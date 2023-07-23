## how to map with AWS IAM role:
ref: https://echorand.me/posts/user-management-aws-eks-cluster/
- aws-auth configmap in kube-system namespace
- cluster creator gets admin privilage by default
- to add other users as ADMIN add following block in aws-auth configmap
    - ``````
    mapUsers: |
        - userarn: arn:aws:iam::AWS-ACCOUN-ID:user/someusername
             username: someusername
             groups:
                 - system:masters
    - user will be added in kubeconfig
        - ```
            apiVersion: v1
            current-context: k8s-cluster
        clusters:
            - cluster:
                certificate-authority-data: < ca data>
                server: < EKS endpoint>
              name: k8s-cluster
            contexts:
            - context:
                cluster: k8s-cluster
                namespace: projectA-qa
                user: username1
              name: username1
            kind: Config
            users:
            - name: username1
              user:
                exec:
                  apiVersion: client.authentication.k8s.io/v1alpha1
                  command: aws-iam-authenticator
                  args:
                  - token
                  - -i
          - k8s-cluster


- [ ] in ==aws-auth== configmap, **IAM role** will be added to **group**
- [ ] in ==clusterrole==, **permissions** will be added
- [ ] in ==clusterrolebinding==, **clusterrole** will be matched with **group**
- [ ] IAM role -> cluster group ->  rolebinding <- clusterrole <- permissions

- [ ] `{{SessionName}}` is added to username to find out the actual user who assumed the role from cloudtrail logs
