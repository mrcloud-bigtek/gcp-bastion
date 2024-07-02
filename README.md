# gcp-bastion
xem port listen on Macos:
   netstat -p tcp -van | grep '^Proto\|LISTEN'

**# case 1: bastion connect to gke private cluster use proxy**
  Step 1: Connect with bastion via IAP tunnel secure with port 8888 (endpoint gke controller). On localhost (client) run:
    gcloud compute ssh bastion --tunnel-through-iap --project=onstudio-dev --zone=asia-southeast1-b --ssh-flag="-4 -L8888:localhost:8888 -N -q -f"
  Step 2: 
    
    
---------
De tranh xung dot giua gcloud va kubect voi bastin host proxy:
- Treen localhost chay cac lenh:
   - gcloud config set proxy/type http

   - gcloud config set proxy/address localhost

   - gcloud config set proxy/port 8888
