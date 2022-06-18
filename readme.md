# How to generate your blog
- hexo clean
- hexo g
- hexo d

# How to backup blog
- git co hexo (backup branch: hexo)
- rm -rf node_modules && npm install --force
- generate your blog
- git add .
- git push

# references
http://hexo.io/docs/