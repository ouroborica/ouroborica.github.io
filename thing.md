# SYNC (Spaces & Units) 

* Past year: 
    **error! (any weird data stays weird...)**
* Current year: 
    1. Spaces 
        * **QUESTION:** deletes can happen when spaces get split/added mid year
            * locked vs unlocked behavior? 
            * leave but only *display* when existing entrata id?
            * Try to only delete the year assocations for missing?
        * Upsert by entrata id 
            **NOTES** 
                * can change name / unit number of past! so needs to rely on historical in DBT
    2. Unit Types:
        * **QUESTION:** deletes: does this happen?  When?
        * Upsert by entrata id (name changes or new/migrated properties)
            **NOTES** 
                * can change name / unit number of past! so needs to rely on historical in DBT
        
    3. attempt to rematch existing UTSO with new/existing space configuration 
* Future year: 
    1.  Spaces: 
        1. **Delete all** that *only* have assocation for that year 
        2. Upsert by entrata id:
            **NOTES:**
            * can change name/unit number of current & past! so needs to rely on historical in DBT
            * going forward duplicates for that name and/or entrata id but should be unique by year
    2. Unit Types:
        1. Delete all that *only* have assocation for that year    
        2. Upsert by entrata id
            **NOTES:**
            * can change of current & past so needs to rely on historical in DBT
            * going forward duplicates for that name and/or entrata id but should be unique by year
    3. **Delete all** assocations for year
    4. Attempt to match "new" types with "new" space configuration


# IMPORT RATES (UTSOs)
* Past year:  
    * interesting feature to add that I dont want to think about implications
* Current year: 
    * slightly more interesting feature to add that we should consider for mid year changes eventually
* Future year:  
    1. Delete all UTSOs
    2. Create UTSOs based on **existing** Unit Types
        * Potentially interesting features:
            - allow to manually choose match
            - create for *some* reason
    3. Do **sync** to attempt association 



