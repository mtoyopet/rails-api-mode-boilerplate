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

1. 