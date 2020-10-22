# Opening ports

When you are working on two different machines they will need to be able to communicate between each other. To do this they will need a port opening.

1. Identify the port that you need to open. For example in the *chat server* lab you need to open port `8030`.

2. Select the instance from the list of instances in your account.

3. Go to the security tab.

![Security Tab](content/security-tab.png)

4. Select the security group, it should load a new page.

![Security Group](content/security-group.png)

5. Click on "Edit inbound rules"

6. Select "Add rule".

7. Set the port range to be the port that you need to open, in the example above it is `8030`.

8. Set the source to be `anywhere`.

9. Click "Save rules".
