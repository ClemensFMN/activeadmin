---
redirect_from: /docs/documentation.html
---

Active Admin is a framework for creating administration style interfaces. It
abstracts common business application patterns to make it simple for developers
to implement beautiful and elegant interfaces with very little effort.

# Getting Started

Active Admin is released as a Ruby Gem. The gem is to be installed within a Ruby
on Rails application. Active Admin does not provide authentification; this is done 
by other gems (e.g. devise). To install without any authentification, simply 
add the following to your Gemfile:

```ruby
# Gemfile
gem 'activeadmin'
```

After updating your bundle, run the installer

```bash
rails generate active_admin:install --skip-users
```

The installer creates an initializer used for configuring defaults used by
Active Admin as well as a new folder at `app/admin` to put all your admin
configurations.

Migrate your db and start the server:

```bash
$> rake db:migrate
$> rails server
```

Visit `http://localhost:3000/admin` and voila: You&#8217;re on your brand 
new Active Admin dashboard.

To register an already existing model, run:

```bash
$> rails generate active_admin:resource [MyModelName]
```

This creates a file at `app/admin/my_model_names.rb` for configuring the
resource. Refresh your web browser to see the interface. In order to CRUD
items, tweak the parameter `permit_params` in `app/admin/MyModel.rb`.

## Usage with devise

If you want to use the devise gem for (admin) authentification, add it to
your Gemfile

```ruby
# Gemfile
gem 'activeadmin'
gem 'devise'
```

Update the bundle and run the installer

```bash
rails generate active_admin:install
```

Migrate your db

```bash
$> rake db:migrate
```

If you are adding devise with Active Admin, you need to seed the database
with an admin user for Active Admin (otherwise you probably will already
have an admin user)

```bash
$> rake db:seed
```

and start the server

```bash
$> rails server
```

Visit `http://localhost:3000/admin` and log in using (this user has been generated
by the database seed):

* __User__: admin@example.com
* __Password__: password

Adding existing models to Active Admin works as described above.


# Next Steps

Now that you have a working Active Admin installation, learn how to customize it:

* [Customize the Index Page](3-index-pages.md)
* [Customize the New and Edit Form](5-forms.md)
* [Customize the Show Page](6-show-pages.md)
* [Customize the Resource in General](2-resource-customization.md)
