# grafana-upgradation

```
grafana upgradation concept :

migration from 7.2 to 7.5 

if sqlite
copy /var/lib/grafana/grafana.db from old to new


          volumeMounts:
            - mountPath: /var/lib/grafana
              name: grafana-pv
            - mountPath: /etc/grafana/grafana.ini
              name: config
      volumes:
        - name: grafana-pv
          hostPath:
            path: /root/grafana
            type: Directory
        - name: config
          hostPath:
            path: /root/grafana/grafana.ini

chown -R 472:472 /var/lib/grafana
or 
chown -R grafana:grafana /var/lib/grafana

migration from 7.2 to 8 same procedure.

to enable unified alerting 
vi grafana.ini
[unified_alerting]
enabled = true


