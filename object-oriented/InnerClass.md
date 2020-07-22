## InnerClass

内部类可以对外部类的成员变量进行访问，外部类不能访问内部类；

### Member InnerClass

#### non-static

    public class nonStaticMemberInnerClass {
        public static void main(String[] args) {
            Outer.Inner inner = new Outer().new Inner();//与静态成员内部类格式不同
            inner.show();
        }
    }
    class Outer{
        private int age = 15;
        class Inner{
            private int age = 20;
            public void show() {
                int age = 30;
                System.out.println("外部类的成员变量age:" + Outer.this.age);
                System.out.println("内部类的成员变量age:"+ this.age);
                System.out.println("局部变量age:"+ age);
            }
        }
    }

#### static
static与non-static修饰符、新建对象格式，其他大体一致；
new格式为：`Outer.Inner inner = new Outer.Inner();`

## Anonymous InnerClass
    public class TestAnonymousInnerClass {
        public static void main(String[] args) {
            test01(new AA() {
                @Override
                public void aa() {
                    System.out.println("none");
                }
            });
        }
    public static void test01(AA a){
        a.aa();
        }
    }
    interface AA{
        void aa();
    }