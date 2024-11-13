# Diffs:
v1 Pod default/nginx-pod-a:
--- default/nginx-pod-a : existing
+++ default/nginx-pod-a : updated
@@ -6,7 +6,8 @@
 spec:
   containers:
   - image: nginx:1.7.9
     name: nginx
     ports:
+    - containerPort: 80
     - containerPort: 8080
 
# Compliance messages:
NonCompliant; violation - pods [nginx-pod-a] found but not as specified in namespace default
