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
  :login => 'TestMerchant',
  :password => 'password')
amount = 1000
credit_card = ActiveMerchant::Billing::CreditCard.new(
  :first_name => 'Bob',
  :last_name => 'Bobsen',
  :number => '424242424242424242',
  :month => '8',
  :year => Time.now.year+1,
  :verification_value => '000')
if credit_card.validate.empty?
  response = gateway.purchase(amount, credit_card)
  if response.success?
    puts "Successfully charged $#{sprintf("%.2f", amount / 100)} to the credit card #{credit_card.display_number}"
  else
    railse StandardError, response.message
  end
end


```

```ruby
gateway = SomeGateway.new
response = gateway.purchase(1000, credit_card)

if response.success?
  puts "Payment complete!"
else
  puts "Payment failed: #{response.message}"
end

credit_card = ActiveMerchat::Billing::CreditCard.new(
  :first_name => 'Steve',
  :last_name => 'Smith',
  :month => '9',
  :year => '2022',
  :brand => 'visa',
  :number => '4242424242424242',
  :verification_value => '424')
  
credit_card = ActiveMerchant::Billing::CreditCard.new(params[:credit_card])

```
