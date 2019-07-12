FROM frolvlad/alpine-python3

RUN wget "https://github.com/HommeOursPorc/tuxart/releases/download/3.2.1/tuxart-3.2.1.tar.gz"
RUN apk add --no-cache python3-dev
RUN apk add --no-cache jpeg-dev zlib-dev freetype-dev lcms2-dev openjpeg-dev tiff-dev tk-dev tcl-dev
RUN apk add --no-cache build-base cairo-dev cairo cairo-tools
RUN apk add --no-cache bash
RUN pip3 install tuxart-3.2.1.tar.gz --user --install-option="--install-scripts=/usr/local/bin/"
RUN wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.13.3.tar.xz 
RUN tar -xJf linux-4.13.3.tar.xz
RUN apk add --no-cache imagemagick
RUN apk add freetype freetype-dev 