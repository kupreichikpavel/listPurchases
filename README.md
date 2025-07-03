# listPurchases
 // список покупок в магаз
      
        Scanner scanner = new Scanner(System.in);
        List<String> list = new ArrayList<>();
        while (true) {
            printMenu();
            int choice = scanner.nextInt();
            switch (choice) {
                case 1:
                    if (list.isEmpty()) {
                        System.out.println("Cписок покупок пуст");
                    } else printList(list);
                    break;
                case 2:
                    scanner.nextLine();
                    System.out.println("Впишите новую покупку в список");
                    String task = scanner.nextLine();
                    list.add(task);
                    System.out.println("Добавлено");
                    break;
                case 3:
                    if (list.isEmpty()) {
                        System.out.println("Ничего нельзя удалить");
                        break;
                    }
                    System.out.println("Выберите товар который хотите удалить");
                    printList(list);
                    choice = scanner.nextInt();
                    list.remove(choice - 1);
                    System.out.println("Товар удален");
                    break;
                case 4:
                    System.out.println("goodbye my lover");
                    return;
                default:
                    System.out.println("Произошла какая-то ошибка.Введите ваш выбор заново");
            }
        }
    }

    public static void printMenu() {
        System.out.println("---------------");
        System.out.println("_Твоя менюшка_");
        System.out.println("1. Показать весь список");
        System.out.println("2. Добавить товар");
        System.out.println("3. Удалить товар");
        System.out.println("4. Выйти");
        System.out.println("---------------");
    }

    public static void printList(List<String> list) {
        System.out.println("Ваша корзина:");
        for (int i = 0; i < list.size(); i++) {
            System.out.println((i + 1) + ". " + list.get(i));
        }
