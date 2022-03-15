### 18. Setting Up Auth Reducer & Actions

* Add auth.actions.ts
* 2 routes for creating a new user in handleAuthenticate
  * dispatch created user
  * or attach pieces required to create an User

### 19. Dispatching Auth Actions

* Dispatching within Auth Service
* Update all the places with this.user.next with the dispatch action
* Side Effect: Not directly connected to state
  * E.g localStorage