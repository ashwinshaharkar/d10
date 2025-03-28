# Use a stock Docksal image as the base
FROM docksal/cli:php8.3-3.8

# nvm/node/npm are only available in the docker user context
USER docker

# Install additional global npm dependencies
RUN set -e; \
  # Initialize the user environment (this loads nvm)
  . $HOME/.profile; \
  # Use composer version 2.x
  sudo composer selfupdate --2; \
  # Install the necessary nodejs version
  nvm install 20.10.0; \
  nvm alias default 20.10.0; \
  # Install packages
  npm install -g yarn gulp-cli;

# Always switch back to root in the end
USER root
