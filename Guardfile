notification :off
interactor :coolline

guard 'spork' do
  watch('Gemfile')
  watch('spec/spec_helper.rb')     { :rspec }
  watch(%r{^spec/support/.+\.rb$}) { :rspec }
end

guard 'rspec', version: 2, cli: "--color --drb --format Fuubar", all_on_start: false, all_after_pass: false do
  watch(%r{^spec/unit/.+_spec\.rb$})
  watch(%r{^spec/acceptance/.+_spec\.rb$})

  watch(%r{^lib/(.+)\.rb$})                     { |m| "spec/unit/#{m[1]}_spec.rb" }
  watch('spec/spec_helper.rb')                  { "spec" }
  watch(%r{^spec/support/.+\.rb$})              { "spec" }
  watch(%r{^spec/shared_examples/(.*)\.rb$})    { |m| ["spec/unit/#{m[1]}_spec.rb", "spec/unit/#{m[1]}"] }
end