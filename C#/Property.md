# Property
- 정보를 은닉하게 위해 보통 클래스의 요소에 직접 접근을 막고 무결성을 보장하기 위해 "getter", "setter" 개념을 사용하곤 했음
    ``` C#
    // class 선언 시
    class Person
    {
        // name 은닉화
        private string name;
        // setter
        public void SetName(string name)
        {
            this.name = name;
        }
        // getter
        public string GetName()
        {
            return this.name;
        }
    }
    // 사용 시
    class Program
    {
        public static void Main(string[] args)
        {
            Person p1 = new Person();
            p1.SetName("Jack");
            Console.WriteLine(p1.GetName);
        }
    }
    ```

- C#에서는 이러한 함수를 줄여쓸 수 있게 property라는 개념을 제공함
    ```C#
    // class 선언 시
    class Person
    {
        private string name;
        public string Name
        {
            get
            {
                return name;
            }
            set
            {
                name = value;
            }
        }
    }
    // 사용 시
    class Program
    {
        public static void Main(string[] args)
        {
            Person p1 = new Person();
            // set과 get에 대해서 알아서 판단하여
            // 메소드로서 동작함
            // private이지만 직접 대입
            p1.Name = "Jack";
            Console.WriteLine(p1.Name);
        }
    }
    ```

- 또한 이러한 함수를 다시 줄여쓸 수 있게 자동 구현 프로퍼티도 제공 ( 7.0 > )
    ``` C#
    class Person
    {
        private string name;
        public string Name { get; set; }
    }

    // 프로퍼티 선언과 기본 값 설정
    class Person
    {
        private string name;
        public string Name { get; set; } = "Jack";
    }
    ```