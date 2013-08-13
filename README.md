# rubypress

[![Gem Version](https://badge.fury.io/rb/rubypress.png)](http://badge.fury.io/rb/rubypress)

This implements the [WordPress XML RPC API](http://codex.wordpress.org/XML-RPC_WordPress_API) as released in version 3.4.

WARNING: SSL is NOT enabled by default for ease of testing for those running OS X systems without setup SSL certs. If this is important to you, checkout the options for instantiating a new client where you can set :use_ssl to true.


## Getting Started

1. Install the gem using specific_install or Bundler

    A. To your system
    
    `gem install rubypress`

    B. Or using Bundler

    Inside your Gemfile:

    `gem 'rubypress'`

2. Create a new client

   ```ruby
   >wp = Rubypress::Client.new(:host => "yourwordpresssite.com", :username => "yourwordpressuser@wordpress.com", :password => "yourwordpresspassword")
   ```

3. Make requests based off of the [WordPress XML RPC API Documentation](http://codex.wordpress.org/XML-RPC_WordPress_API)

    ```ruby
    >wp.getOptions

    => {"software_name"=>{"desc"=>"Software Name", "readonly"=>true, "value"=>"WordPress"}
    ```

    (just a small excerpt of actual options for the sake of the whole brevity thing)`

    ```ruby
    >wp.newPost(:blog_id => "your_blog_id", :content => { :post_status => "publish", :post_date => Time.now, :post_content => "What an awesome post", :post_title => "Woo Title" })  

    => "24"  
    ```

    (returns a post ID if post was successful)

To make further requests, check out the documentation - this gem should follow the exact format of the [WordPress XML RPC API](http://codex.wordpress.org/XML-RPC_WordPress_API).


## Contributing to rubypress

Pull requests welcome.
 
* Check out the latest master to make sure the feature hasn't been implemented or the bug hasn't been fixed yet.
* Check out the issue tracker to make sure someone already hasn't requested it and/or contributed it.
* Fork the project.
* Start a feature/bugfix branch.
* Commit and push until you are happy with your contribution.
* Make sure to add tests for it. This is important so we don't break it in a future version unintentionally.


## Credits

* Zach Feldman [@zachfeldman](http://twitter.com/zachfeldman)
* Dan Collis-Puro (dan@collispuro.com)


### License

Licensed under the same terms as WordPress itself - GPLv2.

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/ed093654d3f4ac89d05750e3def34190 "githalytics.com")](http://githalytics.com/zachfeldman/rubypress)
