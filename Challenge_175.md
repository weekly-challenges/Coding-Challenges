Challenge: 175

Implement a Stack (Last In First Out i.e. LIFO) using two Queue.

#coding #challenge #easy

Solution Attempt #1: (In Java):

```
import java.util.LinkedList;
import java.util.Queue;

public class QueueImpl {

  public static void main(String[] args) {
    QueueImpl queue = new QueueImpl();
    queue.push(1);
    queue.push(2);
    System.out.println(queue.top());
    System.out.println(queue.pop());
    System.out.println(queue.empty());
  }

  Queue<Integer> in_queue = new LinkedList<>();
  Queue<Integer> out_queue = new LinkedList<>();

  public void push(int x) {
    if (!in_queue.isEmpty()) {
      in_queue.add(x);
    } else {
      out_queue.add(x);
    }

  }

  public int pop() {
    int last_item = -1;
    if (!in_queue.isEmpty()) {
      while (!in_queue.isEmpty()) {
        last_item = in_queue.poll();
        out_queue.add(last_item);
      }
      out_queue.remove(last_item);
    } else {
      while (!out_queue.isEmpty()) {
        last_item = out_queue.poll();
        in_queue.add(last_item);
      }
      in_queue.remove(last_item);
    }
    return last_item;
  }

  public int top() {
    int last_item = -1;
    if (!in_queue.isEmpty()) {
      while (!in_queue.isEmpty()) {
        last_item = in_queue.poll();
        out_queue.add(last_item);
      }
    } else {
      while (!out_queue.isEmpty()) {
        last_item = out_queue.poll();
        in_queue.add(last_item);
      }
    }
    return last_item;
  }

  public boolean empty() {
    if (!in_queue.isEmpty()) {
      return false;
    } else {
      return out_queue.isEmpty();
    }
  }
}
```
