# Elasticache
In memory cache

* Supports:
  * Memcached
    * Use if:
      * Object caching is your primary goal
      * You want to keep things as simple as possible
      * You want to scale your cache horizontally (scale-out)
  * Redis
    * User if:
      * You have advanced data types such as lists, hashes and sets
      * You are doing data sorting and ranking such as leader boards
      * Data persistence
      * Multi AZ
      * Pub/Sub capabilities are needed