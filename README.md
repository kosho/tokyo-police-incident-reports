# Tokyo Police Incident Report - Elasticsearch Dashboarding Sample

## Data Source

- Copyright: Metropolitan Police Department of Tokyo, Japan
- Source: [警視庁のメールけいしちょう(登録無料)](http://www.keishicho.metro.tokyo.jp/about_mpd/joho/mail_info.html)
- License: [CC BY 2.1 JP](https://creativecommons.org/licenses/by/2.1/jp/)

## Files

- README.md - this file
- tokyo-police-incident-reports-logstash.conf - Logstash config
- tokyo-police-incident-report-template.json - index template
- tokyo-police-incident-reports-dashboard.json - Kibana dashboard
- tokyo-police-incident-reports-visualizations.json - Kibana visualizations

## Usage

1. Register [the Incident Reporting Service](http://www.keishicho.metro.tokyo.jp/about_mpd/joho/mail_info.html) and receive reports by your mail box
2. Import the japan township level gis information as instructed [here](http://github.com/kosho/japan-township-level-giis)
3. Install `logstash-filter-elasticsearch` plugin as below

  $ bin/logstash-plugin install logstash-filter-elasticsearch

4. Configure the imap input of `tokyo-police-incident-reports-logstash.conf` in order to access to your mail box
5. Configure the elasticsearch output of `tokyo-police-incident-reports-logstash.conf` to point out an appropriate Elasticsearch node
6. Run logstash command as below

  $ logstash -f tokyo-police-incident-reports-logstash.conf

7. Press C-c to stop the logstash process
8. Import `tokyo-police-incident-reports-dashboard.json` and `tokyo-police-incident-reports-visualizations.json` from Kibana object settings

