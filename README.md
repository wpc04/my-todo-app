# my-todo-app
import java.util.ArrayList;
import java.util.Scanner;

public class TodoApp {
    public static void main(String[] args) {
        ArrayList<String> todos = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        System.out.println("📝 欢迎使用待办事项！");

        while (true) {
            System.out.println("\n1. 添加任务");
            System.out.println("2. 查看所有任务");
            System.out.println("3. 退出");
            System.out.print("请输入选项：");

            int choice = scanner.nextInt();
            scanner.nextLine();

            if (choice == 1) {
                System.out.print("请输入任务内容：");
                String task = scanner.nextLine();
                todos.add(task);
                System.out.println("✅ 添加成功！");
            } else if (choice == 2) {
                System.out.println("\n--- 你的任务 ---");
                if (todos.isEmpty()) {
                    System.out.println("暂无任务，快去添加吧！");
                } else {
                    for (int i = 0; i < todos.size(); i++) {
                        System.out.println((i + 1) + ". " + todos.get(i));
                    }
                }
            } else if (choice == 3) {
                System.out.println("👋 再见！");
                break;
            } else {
                System.out.println("❌ 无效选项，请重新输入。");
            }
        }
        scanner.close();
    }
}
