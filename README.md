


----------


*Rules of thumb:*
-----------------

**Memory Optimizations**

	> Cache misses are the most deadly part of building a well optimized game using this Dynasty. A CPU are extremely fast, but RAM is yet to catch up. These are caused by the CPU not having the memory it's trying to grab at that time in it's cache, thus causing a cache miss which makes it go to the RAM to get it's data (which is slow).

> When creating collections that have to be iterated over, containing objects which have active states, it is ideal to create separate collections containing the active & inactive objects.

    public List<Entity> ActiveEntities;
    public List<Entity> InactiveEntities;

Array Of Bytes
> The order of memory is extremely important, when using classes a pointer is created to a location in memory which doesn't guarantee to be placed around other objects of the same type. This is an issue due to how your CPU will grab from the RAM in chunks(collecting data also around it), then store it in your CPU cache. If the next object you're grabbing is not around it in memory, it will have to go back to the RAM to grab it.
