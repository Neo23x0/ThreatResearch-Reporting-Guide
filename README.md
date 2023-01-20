# ThreatResearch-Reporting-Guide

Offensive Research Guide to Help Defense Improve Detection

Whenever you research a certain vulnerability ask yourself these questions and please answer them for us

## Logging

Does the exploited service write a log? \
  (check ls -lrt /var/log or lsof +D /var/log/ or lsof | grep servicename)
  
Does a system service write a log? \
  (e.g. check with tail -f /var/log/messages)
  
Does it write an event in that log for an exploitation attempt?

Does additional logging/configuration requires enabling? \
   (e.g. access logs need to be configured to include uri_query)

Does it write an event in case of successful exploitation?

Does that log line contain specific values that shouldn't normally appear in similar log lines? \
  (e.g. empty source address, uncommon characters)

Please include an example log line

## Other Traces

Does exploitation generate other events that are directly caused by my actions? (e.g. user login)

Does exploitation create temporary files? (e.g. an XML in a temp folder)

## Provide Help

Could you provide simple shell commands to check if someone has previously expolited that vulnerability? \
  (e.g. egrep "specific-url" /var/log/service.log, zgrep "specific-url" /var/log/service/*.gz)
  
Could you provide a quick fix that can block explots until the vendor provides a solution? \
  (e.g. add line in server-side script to drop all requests that contain ":;" in their User-Agent field)
  
