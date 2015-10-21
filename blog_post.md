ENCAPSULATION
=============
What is Encapsulation in Ruby?
------------------------------
Encapsulation is the packing of data and functions into a single component. Essentially this means the inner workings and data of an object are hidden from the outside world, with only those elements that the outside world needs access to being exposed. Encapsulation results in a more secure codebase, with less risk of a user modifying the code or using it in a way that was not intended.

An example of a poorly-encapsulated class
-----------------------------------------
```ruby
Class User
  attr_accessor :username, :password

  def initialize(correct_username, correct_password)
    @username, @password = correct_username, correct_password
  end

  def log_on(email, pw)
    'successful' if (username == email && password == pw)
  end
end
```
This is a poor example of encapsulation as the `username` and `password` variables are unnecessarily exposed through an attr_accessor, allowing them to be changed externally. This could allow someone that does not know the correct username & password combination to reset these to whatever value they like and then log on successfully.

To refactor this you would simply remove the attr_accessors.
