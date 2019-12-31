Had to update ruby gem bundler with command "RUN bundle update --bundler", otherwise nokogiri package would fail for whatever reason.
Also had to add SECRET_KEY_BASE env var, otherwise rails db:migrate would fail.
