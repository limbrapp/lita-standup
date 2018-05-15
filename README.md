# lita-standup

Provides a structured standup discussion to share amongst team members, along with scheduling at specific times/days for each user.

The original code for this library was constructed by [Josh Bassett](https://twitter.com/nullobject) and others at [The Conversation](https://theconversation.com/au), and then generously shared with myself to extend and open source.

It has been written with Slack in mind as the adapter, but extensions to make it more friendly with other platforms are very welcome.

## Usage

This handler adds the following public commands via direct messages to your Lita bot:

* `standup` – begins a standup conversation with three questions (what have you been working on, what's next, what's getting in the way). Once these questions are answered, the result is shared in the target channel.
* `standup schedule` – see your personal schedule for standup conversations.
* `standup schedule TIME DAY DAY DAY` – set your personal schedule for standup conversations. e.g. `standup schedule 10:00 monday tuesday friday`. All days are accepted, and the time is 24 hours, and respects the user's time zone if set (otherwise, defaults to UTC).

If you want to get stuck into the internals of this handler, there are two hidden commands that may be useful:

* `standup export` – returns the JSON of each person's schedules.
* `standup import JSON` – sets up everyone's schedules. Don't use this command unless you're absolutely sure of what you're doing.

## Installation

Add lita-standup to your Lita instance's Gemfile:

```ruby
gem "lita-standup"
```

Then, in your Lita configuration, you'll want to set the channel where standup messages are shared:

```ruby
config.handlers.standup.target = "standup"
```

## Contributing

Bug reports and pull requests are welcome [on GitHub](https://github.com/limbr/lita-standup). This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

lita-standup is developed and maintained by [Pat Allan](https://freelancing-gods.com) for [Limbr](https://limbr.org), based on code by the team at [The Conversation](https://theconversation.com/au), and is released under the open [MIT Licence](https://opensource.org/licenses/MIT).
