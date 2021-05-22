#  SPDX-License-Identifier: AGPL-3.0-only

#  Copyright (C) 2021  Patrick McLean - psmware ltd

#  This program is free software: you can redistribute it and/or modify
#  it under the terms of the GNU Affero General Public License as published by
#  the Free Software Foundation, either version 3 of the License, or
#  (at your option) any later version.

#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU Affero General Public License for more details.
FROM psmwareltd/python:3.9.5
LABEL author="Pat McLean" \
      maintainer="Pat McLean<github@psmware.ie>"


USER root
# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install --no-install-recommends -y postgresql-client
RUN echo "===> Cleaning up package list..." \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN echo "===> Installing Python Packages tools... "
ARG USERNAME=vscode
WORKDIR /tmp
USER ${USERNAME}
COPY ./pyproject.toml /tmp/pyproject.toml
RUN /home/$USERNAME/.poetry/bin/poetry lock
RUN /home/$USERNAME/.poetry/bin/poetry install

