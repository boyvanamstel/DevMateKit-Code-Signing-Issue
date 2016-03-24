platform :osx, '10.11'

pod 'DevMateKit', '1.7' #, '1.5'

post_install do |installer|
  system("RUBY_SCRIPT='Pods/DevMateKit/copy_xpc_build_phase.rb'; if [ -f $RUBY_SCRIPT ]; then ruby $RUBY_SCRIPT '#{path}'; fi")
end
