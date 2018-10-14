### ActiveMerchant
---

https://github.com/activemerchant/active_merchant

```
git clone git://github.com/activemerchant/active_merchant.git
gem install activemercahnt
gem 'activemerchant'
```

```ruby
require 'active_merchant'
ActiveMerchant::Billing::Base.mode = :test
gateway = ActiveMerchant::Billing::TrustCommerceGateway.new(
  :login => '',
  :password => '')
amount = 1000
credit_card = ActiveMerchant::Billing::CreditCard.new(
  :first_name => '',
  : => '',
  : => '',
  : => '',
  : => '',
  : => '', 
  : => '', 
  : => '', 
  : => '')
if credit_card.validate.empty?
  response = gateway.purchase(amount, credit_card)
  if response.success?
    puts "Successfully charged $#{sprintf("%.2f", amount / 100)} to the credit card #{credit_card.display_number}"
  else
    railse StandardError, response.message
  end
end


```

```

```
