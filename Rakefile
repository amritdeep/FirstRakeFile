directory "tmp"

file "hello.tmp" => "tmp" do
	sh "echo 'Hello' >> 'tmp/hello.tmp'"
end

task :default => 'morning:ready_for_work'

namespace :morning do
	
	desc "Turn Off Alarm"
	task :turn_off_alarm do
		puts "Turn off the alarm please"
	end

	desc "Groom Myself"
	task :groom_myself do
		puts "wake up"
		puts "Brushed teeth"
		puts "showered"
		puts "shaved"
	end

	desc "Make Coffee"
	task :make_coffee do
		cups = ENV["COFFEE_CUPS"] || 2
		puts "Made #{cups} cups of coffee. Shakes are gone."
	end

	desc "Ready for Work"
	task :ready_for_work => [:turn_off_alarm, :groom_myself, :make_coffee] do
		puts "Ready for Work"
	end
end

namespace :evening do
	
	desc "Go to home"
	task :go_to_home do
		puts "Going Home"
	end

	desc "Take rest"
	task :take_rest do
		min = ENV["TIME"] || 60
		puts "Take a rest for #{min} min"
	end

	desc "Cook Dinner"
	task :cook_dinner do
		puts "Cooking Dinner"
	end

	desc "Sleep"
	task :sleep => [:go_to_home, :take_rest, :cook_dinner] do
		puts "Sleeping"
	end

end

namespace :all_day do
	desc "A Day"
	task :day => ['morning:ready_for_work', 'evening:sleep'] do
		puts "All day"	
	end
end



