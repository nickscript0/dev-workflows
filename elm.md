## Dev Notes
### Importing a tagged union from another module:
```elm
-- Tagged union in Module B
type SearchResult = NotFound
                  | Found FightResult
                 

-- Can be imported with or without its tags in Module A
-- With its tags
import B exposing (SearchResult(..))

-- Without its tags
import B exposing (SearchResult)
```
