# laboratorium-13

Po zainstalowaniu helm wykonujemy następujące polecenia:

1) helm pull bitnami/nginx
2) helm install -f nginx/values.yaml my-nginx nginx/  (tutaj musimy przejść do rozpakowane katalogu <u mnie nginx-15.9.0> i dopiero wydać polecenie)

Zainstaluje to nam podstawową wersję (z LoadBalancerem)

Aby przestawić serwis na Ingress musimy:

1) Zmienić plik values.yaml - linijka 627 w pliku values.yaml. Należy skonfigurować oraz aktywować ingress.
   
ingress:
  enabled: true
 

2) Następnie należy zmodyfikować typ z LoadBalancer na ClusterService - linijka 556 w oryginalnym pliku values.yaml

service:
  type: ClusterIP


Następnie robimy update :  helm upgrade -f nginx/values.yaml my-nginx nginx/

![helm-upg](https://github.com/kamil4444/laboratorium-13/assets/103449118/273a56a5-dce0-451e-997e-949ff3e78d28)
![helm-upg2](https://github.com/kamil4444/laboratorium-13/assets/103449118/05ca6ab9-5f14-459c-8e68-bf034ce3b260)

