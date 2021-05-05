## STEPS

### 1. Railsプロジェクトを作成する

参考: [新規Railsプロジェクトの作成手順まとめ](https://qiita.com/yuitnnn/items/b45bba658d86eabdbb26)

1. `mkdir live-chat-api` 
2. Gemファイルで`gem "rails"`を`gem 'rails', '~> 6.0.0'`に変更
3. `bundle install --path vendor/bundle`
4. Railsアプリを作成 `bundle exec rails new . --api`
  - `Overwrite /Users/mtoyopet/code/personal-project/2021/techpit/live-chat-api/Gemfile?` は`Y`を選択

### 2. ログイン機能を実装する

参考: [Rails6.0とdevice_token_auth でトークンベースで認証を実装する](https://qiita.com/mtoyopet/items/076b623ac72f4f83c5f6)

1. deviseとdevise_token_authをGemfileに追加。rubygems.orgから最新を追加すること
2. `bundle install`、`bundle exec rails g devise:install`を実行
  ```
  Running via Spring preloader in process 45327
    conflict  config/initializers/devise.rb
  Overwrite /Users/mtoyopet/code/personal-project/2021/techpit/live-chat-api/config/initializers/devise.rb? (enter "h" for help) [Ynaqdhm] Y
        force  config/initializers/devise.rb
    identical  config/locales/devise.en.yml
  ===============================================================================

  Depending on your application's configuration some manual setup may be required:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.

     * Required for all applications. *

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"
     
     * Not required for API-only Applications *

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:

       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

     * Not required for API-only Applications *

  4. You can copy Devise views (for customization) to your app by running:

       rails g devise:views
       
     * Not required *

  ===============================================================================
  ```
3. `bundle exec rails g devise_token_auth:install User auth`を実行
  ```
  Running via Spring preloader in process 45488
  create  config/initializers/devise_token_auth.rb
  insert  app/controllers/application_controller.rb
    gsub  config/routes.rb
  create  db/migrate/20210505052353_devise_token_auth_create_users.rb
  create  app/models/user.rb
  ```
