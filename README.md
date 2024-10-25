# helm



helm install eks-backend-yeyeye my-helm-repo/eks-backend --version 1.0.1 \
  --set acmCertificateArn="arn:aws:acm:us-east-1:533267127040:certificate/bc088350-8450-478b-bd01-d682317d732e" \
  --set nameOverride="eks-backend" \
  --set env.dbHost="mysql-test-service" \
  --set env.dbUser="root" \
  --set env.dbPassword="publicP15" \
  --set env.dbDatabase="decccvops" \
  --set ingressName="eks-backend-ingress" \
  --set replicaCount=3 \
  --set ingress.hosts[0].host="aws.skyphonez.com.au" \
  --set ingress.hosts[0].paths[0].path="/" \
  --set ingress.hosts[0].paths[0].port=9001 \
  --set ingress.hosts[0].paths[0].serviceName="eks-backend-service-1" \
  --set ingress.hosts[1].host="another.host.com" \
  --set ingress.hosts[1].paths[0].path="/app" \
  --set ingress.hosts[1].paths[0].port=9002 \
  --set ingress.hosts[1].paths[0].serviceName="eks-backend-service-2" \
  --set ingress.hosts[2].host="third.host.com" \
  --set ingress.hosts[2].paths[0].path="/service" \
  --set ingress.hosts[2].paths[0].port=9003 \
  --set ingress.hosts[2].paths[0].serviceName="eks-backend-service-3"
