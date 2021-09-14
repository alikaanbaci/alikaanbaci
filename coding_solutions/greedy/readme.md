> #### Greedy Algorithms

**The algorithm makes the optimal choice at each step as it attempts to find the overall optimal way to solve the entire problem.** Greedy algorithms are quite successful in some problems, such as [Huffman encoding](https://brilliant.org/wiki/huffman-encoding/) which is used to compress data, or [Dijkstra's algorithm](https://brilliant.org/wiki/dijkstras-short-path-finder/), which is used to find the shortest path through a graph.

> ###### **Activity Selection Problem**

*You are given n activities with their start and finish times. Select the maximum number of activities that can be performed by a single person, assuming that a person can only work on a single activity at a time.* 

```java
public class ActivitySelection {

  // Assummed that start and finish array of activities order by finish asc
  public int[] setActivities(int[] start, int[] finish) {

    // Result list
    List<Integer> activities =  new ArrayList<>();
    
    int finishIndex = 0;
    // first activity added because its finish time is smallest one
    activities.add(finishIndex);

    // go trough start time of activities
    for (int startIndex = 1; startIndex < start.length; startIndex++) {
      // if finish time is smaller than last proper activity
      // then add the activity to the activities set finish index 
      // to compare with next activity
      if (finish[finishIndex] < start[startIndex]) {
        activities.add(startIndex);
        finishIndex = startIndex;
      }
    }
    
    // map to integer
    return activities.stream().mapToInt(Integer::intValue).toArray();
  }
}

```

Test Runner

```java
class ActivitySelectionTest {

  @Test
  void setActivitiesTest() {
    ActivitySelection activitySelection = new ActivitySelection();

    int [] start = {1, 3, 0, 5, 8, 5};
    int [] finish =  {2, 4, 6, 7, 9, 9};

    int [] result = {0, 1, 3, 4};

    Assertions.assertArrayEquals(result, activitySelection.setActivities(start, finish));
  }
}
```

