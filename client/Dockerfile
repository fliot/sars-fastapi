FROM node:14.8
COPY . .
RUN npm install --silent
RUN npm run build
RUN npm install -g serve
CMD serve -s build -l $PORT