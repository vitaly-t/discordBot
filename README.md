## discordBot

currency: Tacos

commands:
```
!thank - 2 hours
!sorry - 6 hours
!harvest - 12 hours (based on number of trees)
!bake - 72 hours
!buyTree - x number of tacos
!give
!welcome -
get 2 cookies on ur birthday
```

### structure

for users use discord id
```
!thank
    -check time on last thank
    -if user exists then put
        - call get for user
            - post their current # of tacos
    -if user doesnt exist then post
        - add 2 to their record
            - call get for user
                - post their current # of tacos
```

```
!sorry
    -same as thank but 6 hours
```

```
!harvest
    - check time on last harvest
    - call get for user
        - if user exists then put x number of tacos (based on number of trees in user acct)
            -post their current # of tacos
        - if user doesnt exist then post msg saying the user cannot harvest any trees
```

```
!bake
    -check time on last bake
    - call get for user
        -if user exists then same thing as above

```

```
!buyTree
    -call get user
        -if user has enough # of tacos then update user acct with - x # of tacos
            -if successful update user with +1 tree
                - if successful post message that user has bought a tree
                - if fail - call update on user and refund their # of tacos

        -if user doesnt have enough # of tacos then post message saying they do not have enough tacos
```

```
!give 
    -call get user
        -if user has enough # of tacos then call get user on @user
            -if user exists then call update and remove tacos from user
                -if sucessful call update on @user and add tacos to user
                -if failure then call update on first user and refund their # of tacos
            -if user doesn't exist then call post and start them with the # number of tacos given
        -if user doesnt have enough # of tacos then post message they do not have sufficient tacos
```