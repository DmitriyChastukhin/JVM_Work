    
`public class` JvmComprehen{

    public static void main(String[] args) {

    int i = 1;                      // 1 во фрейме main создается переменная i типа int со значением 1.
        Object o = new Object();        // 2 в heap (куча) создается объект типа Object, на которую ссылается переменная Object о созданная во фрейме main.

        Integer ii = 2;                 // 3 Переменная ii создается в стэке и хранит в себе ссылку на объект Integer, принимающий значение 2.

        printAll(o, i, ii);             // 4 в стэке создается фрейм printAll. В нём создается примитив i и ссылки на объекты o и ii, сами объекты Object и Integer попадают в heap.

        System.out.println("finished"); // 7 в стэке создается фрейм println,который принимает ссылку типа String на объект из кучи "finished".
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 В куче создается объект типа  Integer со значением 700, на которую ссылается переменная uselessVar созданная во фрейме printAll.

        System.out.println(o.toString() + i + ii);  // 6 в стэке создается фрейм println и примитив i, который принимает ссылки на объекты o и ii, находящиеся в куче, а также значение примитива i. После завершения метода println - фрейм println будет удален.
    }
}