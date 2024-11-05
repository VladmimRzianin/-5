        Console.WriteLine("Введите фамилию:");
        string lastName = Console.ReadLine();
        Console.WriteLine("Введите имя:");
        string firstName = Console.ReadLine();
        Console.WriteLine("Введите отчество:");
        string middleName = Console.ReadLine();

        bool running = true;
        while (running)
        {
            Console.WriteLine("\nВыберите операцию:");
            Console.WriteLine("1 - вытащить фамилию, имя или отчество");
            Console.WriteLine("2 - отсортировать фамилию");
            Console.WriteLine("3 - изменить фамилию, имя или отчество");
            Console.WriteLine("4 - показать полное ФИО");
            Console.WriteLine("5 - показать количество букв в ФИО");

            int choice = int.Parse(Console.ReadLine());

            switch (choice)
            {
                case 1:
                    Console.WriteLine("ввести 'фамилия', 'имя' или 'отчество':");
                    string part = Console.ReadLine().ToLower();
                    if (part == "фамилия") Console.WriteLine("фамилия: " + lastName);
                    else if (part == "имя") Console.WriteLine("имя: " + firstName);
                    else if (part == "отчество") Console.WriteLine("отчество: " + middleName);
                    break;

                case 2:
                    Console.WriteLine("ввести 'возрастание' или 'убывание' для сортировки ");
                    string order = Console.ReadLine().ToLower;
                    lastName = order == "возрастание" ? new string(lastName.OrderBy(c => c).ToArray()) // увел
                                                       : new string(lastName.OrderByDescending(c => c).ToArray()); // уменьш
                    Console.WriteLine("Отсортированная фамилия: " + lastName);
                    break;

                case 3:
                    Console.WriteLine("ввести 'фамилия', 'имя' или 'отчество' для изменения ");
                    part = Console.ReadLine();
                    Console.WriteLine("ввести новое значение ");
                    string newValue = Console.ReadLine();
                    if (part == "фамилия") lastName = newValue;
                    else if (part == "имя") firstName = newValue;
                    else if (part == "отчество") middleName = newValue;
                    break;

                case 4:
                    Console.WriteLine("полное ФИО  " + lastName + " " + firstName + " " + middleName);
                    break;

                case 5:
                    Console.WriteLine($"фамилия ({lastName.Length} букв), имя ({firstName.Length} букв), отчество ({middleName.Length} букв)");
                    break;
            }
        }
