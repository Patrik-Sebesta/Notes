###kde hladať logy containeru ? 
1. Treba najsť správny docker-composer v /opt/tm 
2. v docker-composer je pre každú službu definovaný  'syslog-facility'
3. v /etc/rsyslog.d/[služba] je cesta k logu    