import java.util.ArrayList;
import java.util.Scanner;

public class TodoAPP {
    public static void main(String[] args) {
        ArrayList<String> todos = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        System.out.println("📝 欢迎使用待办事项！");

        while (true) {
            System.out.println("\n1. 添加任务");
            System.out.println("2. 查看所有任务");
            System.out.println("3. 删除任务");
            System.out.println("4. 退出");
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
                if (todos.isEmpty()) {
                    System.out.println("暂无任务可删除！");
                } else {
                    System.out.print("请输入要删除的任务序号：");
                    int index = scanner.nextInt();
                    if (index >= 1 && index <= todos.size()) {
                        String removed = todos.remove(index - 1);
                        System.out.println("🗑️ 已删除：" + removed);
                    } else {
                        System.out.println("❌ 无效序号，请重新输入。");
                    }
                }
            } else if (choice == 4) {
                System.out.println("👋 再见！");
                break;
            } else {
                System.out.println("❌ 无效选项，请重新输入。");
            }
        }
        scanner.close();
    }
}
