require "yast/rake"

Yast::Tasks.configuration do |conf|
  # lets ignore license check for now
  conf.skip_license_check << /.*/
end

# safety check - make sure the RNG file is up to date
task :check_rng_status do
  # get the timestamps for the last commits
  rnc_commit_time = `git log -1 --format="%ct" -- control/control.rnc`
  rng_commit_time = `git log -1 --format="%ct" -- control/control.rng`

  # RNC must not be newer than RNG
  if rng_commit_time.to_i < rnc_commit_time.to_i
    raise "Error: control/control.rng is outdated, regenerate it running \"rake generate_rng\")"
  end
end

desc "Generate the RNG file from the RNC schema"
task :generate_rng do
  unless system("which trang >/dev/null 2>&1")
    raise "Error: trang package is missing, please install it for proceeding with the conversion."
  end

  system("trang -I rnc -O rng control/control.rnc control/control.rng")
end

task tarball: :check_rng_status
