using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        // Tạo danh sách các học sinh
        List<Student> students = new List<Student>
        {
            new Student { Id = 1, Name = "An", Age = 16 },
            new Student { Id = 2, Name = "Bao", Age = 18 },
            new Student { Id = 3, Name="Cuong", Age = 17 },
            new Student { Id = 4,  Name="hung", Age = 15 },
            new Student { Id = 5, Name = "Hoang", Age = 19 }
        };

        // a. In danh sách toàn bộ học sinh
        Console.WriteLine("Danh sach toan bo hoc sinh:");
        foreach (var student in students)
        {
            Console.WriteLine($"ID: {student.Id}, Ten: {student.Name}, Tuoi: {student.Age}");
        }

        // b. Tìm học sinh có tuổi từ 15 đến 18
        Console.WriteLine("\nDanh sach hoc sinh co tuoi tu 15 den 18:");
        var studentsInRange = students.Where(s => s.Age >= 15 && s.Age <= 18);
        foreach (var student in studentsInRange)
        {
            Console.WriteLine($"ID: {student.Id}, Ten: {student.Name}, Tuoi: {student.Age}");
        }

        // c. Tìm học sinh có tên bắt đầu bằng chữ "A"
        Console.WriteLine("\nHoc sinh co ten bat dau bang chu \"A\":");
        var studentsStartWithA = students.Where(s => s.Name.StartsWith("A"));
        foreach (var student in studentsStartWithA)
        {
            Console.WriteLine($"ID: {student.Id}, Ten: {student.Name}, Tuoi: {student.Age}");
        }

        // d. Tính tổng tuổi
        int totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"\nTong so tuoi cua tat ca hoc sinh: {totalAge}");

        // e. Tìm học sinh có tuổi lớn nhất
        var oldestStudent = students.OrderByDescending(s => s.Age).First();
        Console.WriteLine($"\nHoc sinh co tuoi lon nhat: ID: {oldestStudent.Id}, Tên: {oldestStudent.Name}, Tuổi: {oldestStudent.Age}");

        // f. Sắp xếp theo tuổi tăng dần
        Console.WriteLine("\nDanh sach hoc sinh sau khi sap xep theo tuoi tang dan:");
        var sortedStudents = students.OrderBy(s => s.Age);
        foreach (var student in sortedStudents)
        {
            Console.WriteLine($"ID: {student.Id}, Ten: {student.Name}, Tuoi: {student.Age}");
        }
    }
}
