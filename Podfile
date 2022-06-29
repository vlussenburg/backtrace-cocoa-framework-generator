platform :ios, '10.0'

plugin 'cocoapods-rome', { :pre_compile => Proc.new { |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['SWIFT_VERSION'] = '4.2'
            config.build_settings['ENABLE_BITCODE'] = ENV['ENABLE_BITCODE']
            config.build_settings['ALWAYS_EMBED_SWIFT_STANDARD_LIBRARIES'] = ENV['SWIFT_EMBEDDED']
        end
    end

    installer.pods_project.save
},

    dsym: true,
    configuration: 'Release'
}

target 'backtrace' do
  use_frameworks!
  pod 'Backtrace'
end
