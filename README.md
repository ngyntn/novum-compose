### Run this command on window

`scp -i D:/Pems/<key-file> my-aws-key.pem ubuntu@<public-ip>:/home/ubuntu/novum-compose`


### Run this command on ubuntu
`chmod 400 my-aws-key.pem (cấp quyền chỉ đọc cho owner/admin)`


### Run this command on ubuntu
`tmux new -s ssh-tunnel -d`
`ctrl b d`
`tmux ls`
`tmux attach -t ssh-tunnel`

### Run this command on ubuntu
`ssh -i my-aws-key.pem -N -L 0.0.0.0:3307:web-blog-db.cv4cy2ucoenv.ap-southeast-1.rds.amazonaws.com:3306 ubuntu@175.41.189.165`


### Run this command on windown (webblogpassword)
`mysql -h localhost -P 3307 -u admin -p`

### Run this command on windown
`update user_article_interactions set created_at = NOW() where true;`



### Step

1. Change IP in ENV frontend --> build image -> tag | push images.
2. Change IP in docker-compose.yml and frontend image's version. (jano-react-app:v1.1.1)
3. Run tunnel.
4. Docker compose up -d.
5. Update mysql.
6. Access at <public-ip>:5173

(Add security group at 5173, 8080)




