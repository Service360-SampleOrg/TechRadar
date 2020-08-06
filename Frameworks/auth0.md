# Auth0

- Status: TRIAL
- Date: 01.01.2020

Initially implemented to save time on authorisation and it does its 
job quite good + it is pretty cheap.

Found two downsides so far:
- Hard "impossible": not able to support subdomains thru one application
(can't make <org>.service360.io domains)
- Strange behaviour (app is hanging) on login after long inactivity 
time. Thou that might be my implementation bug. Will check later  