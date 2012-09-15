# Heroku Error Pages

A simple Middleman app to generate custom error pages and sync them to S3.

## Local development

```bash
gem install bundler
bundle install
bundle exec middleman
```

## Building and syncing

You need a `.env` file with AWS credentials:

```
FOG_PROVIDER=AWS
FOG_DIRECTORY=some.bucket
FOG_REGION=us-east-1
AWS_ACCESS_KEY_ID=your_key
AWS_SECRET_ACCESS_KEY=your_secret_access_key
```

It's then easy to generate the site and push it up to S3:

```bash
export $(cat .env)
bundle exec middleman build
```