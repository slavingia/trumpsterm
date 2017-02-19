require 'twitter'

desc "Tweet"
task :tweet do
  puts "Tweeting..."

  client = Twitter::REST::Client.new do |config|
    config.consumer_key        = ENV["CONSUMER_KEY"]
    config.consumer_secret     = ENV["CONSUMER_SECRET"]
    config.access_token        = ENV["ACCESS_TOKEN"]
    config.access_token_secret = ENV["ACCESS_TOKEN_SECRET"]
  end

  start_of_term = Date.parse("20-01-2017")
  end_of_term = Date.parse("20-01-2021")
  today = Date.today

  days_so_far = (today - start_of_term).to_i
  days_left = (end_of_term - today).to_i
  days_total = (end_of_term - start_of_term).to_i

  percent_done = (days_so_far.to_f / days_total.to_f * 100).to_i

  bar = ""
  for i in 1..10 do
    bar = "#{bar}" + ((i * 10 > percent_done) ? "░" : "▓")
  end

  tweet = "#{bar} #{percent_done}% done (#{days_left.to_s.reverse.scan(/\d{3}|.+/).join(",").reverse} days to go)"

  client.update(tweet)

  puts "Tweeted: #{tweet}."
end
