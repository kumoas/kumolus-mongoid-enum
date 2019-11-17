# Mongoid::Enum

# Installation

Add this to your Gemfile:

```ruby
gem "kumolus-mongoid-enum"
```

And then run `bundle install`.


# Usage

```ruby
class Payment
  include Mongoid::Document
  include Mongoid::Enum

  enum :status, [:pending, :approved, :declined]
end
```

Aaaaaaand then you get things like:

```ruby
payment = Payment.create

payment.status
# => :pending

payment.approved!
# => :approved

payment.pending?
# => :false

Payment.approved
# => Mongoid::Criteria for payments with status == :approved

```

