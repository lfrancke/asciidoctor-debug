FROM ruby

RUN apt-get -y update && apt-get -y install libicu-dev cmake && rm -rf /var/lib/apt/lists/*
RUN gem install github-linguist
RUN gem install asciidoctor
RUN git clone https://github.com/gollum/gollum && cd gollum && bundle install

WORKDIR /wiki

ENTRYPOINT ["/gollum/bin/gollum", "--port", "80", "--config", "/wiki/gollum/config.rb", "--live-preview", "--page-file-dir", "content"]

EXPOSE 80
