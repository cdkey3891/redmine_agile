Redmine_Agile Light Version from RedmineUP

#cd ~

#git clone https://github.com/cdkey3891/redmine_agile.git

#cp -r ~/redmine_agile /opt/redmine/apps/redmine/htdocs/plugins/

#cd /opt/redmine/apps/redmine/htdocs

#/opt/redmine/use_redmine

$ bundle install --without development test --no-deployment

$ bundle exec rake redmine:plugins NAME=redmine_agile RAILS_ENV=production

$ /opt/redmine/ctlscript.sh restart

Trong trường hợp chạy "bundle install --without development test --no-deployment"
báo lỗi
"An error occurred while installing nokogiri (1.6.7.2), and Bundler cannot continue.
Make sure that `gem install nokogiri -v '1.6.7.2'` succeeds before bundling."

Fix: Chạy
bundle config build.nokogiri --use-system-libraries
Kết quả:
You are replacing the current global value of build.nokogiri, which is currently "--with-opt-dir=/opt/redmine/common"

Sau đó chạy lại
bundle install --without development test --no-deployment

