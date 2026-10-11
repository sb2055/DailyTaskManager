# DailyTaskManager
Daily task manager in IntelliJ
[DailyTaskManager.java](https://github.com/user-attachments/files/33293904/DailyTaskManager.java)
import java.util.Scanner;

class Task {
    private String name;
    private Integer time;
    private Boolean done;

    public Task(String name, Integer time, Boolean done) {
        this.name = name;
        this.time = time;
        this.done = done;
    }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public Integer getTime() { return time; }
    public void setTime(Integer time) { this.time = time; }

    public Boolean getDone() { return done; }
    public void setDone(Boolean done) { this.done = done; }
}

public class DailyTaskManager {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Task[] tasks = new Task[5];

        for (int i = 0; i < 5; i++) {
            System.out.println("Task " + (i + 1));
            System.out.print("Name: ");
            String name = input.nextLine();
            System.out.print("Estimated time (minutes): ");
            Integer time = Integer.valueOf(input.nextLine());
            System.out.print("Completed? (true/false): ");
            Boolean done = Boolean.valueOf(input.nextLine());
            tasks[i] = new Task(name, time, done);
        }

        System.out.println("\n--- Your Tasks ---");
        for (Task t : tasks) {
            System.out.println(t.getName() + " | " + t.getTime() + " min | Completed: " + t.getDone());
        }
    }
}
