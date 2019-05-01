---
title: Lambda İfadeleri Örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- lambda expressions [C++], examples
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
ms.openlocfilehash: 6854c5710d8a27093078c0f2013d691ac22c5870
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392199"
---
# <a name="examples-of-lambda-expressions"></a>Lambda İfadeleri Örnekleri

Bu makalede, lambda ifadelerinin programlarınızda nasıl kullanılacağı gösterilmektedir. Lambda ifadelerine genel bakış için bkz. [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md). Bir lambda ifadesinin yapısı hakkında daha fazla bilgi için bkz. [Lambda ifadesi söz dizimi](../cpp/lambda-expression-syntax.md).

##  <a name="declaringLambdaExpressions"></a> Lambda ifadeleri bildirme

### <a name="example-1"></a>Örnek 1

Bir lambda ifadesi yazıldığından, kendisine atayabilirsiniz bir **otomatik** değişkeni veya bir [işlevi](../standard-library/function-class.md) burada gösterildiği gibi nesne:

### <a name="code"></a>Kod

```cpp
// declaring_lambda_expressions1.cpp
// compile with: /EHsc /W4
#include <functional>
#include <iostream>

int main()
{

    using namespace std;

    // Assign the lambda expression that adds two numbers to an auto variable.
    auto f1 = [](int x, int y) { return x + y; };

    cout << f1(2, 3) << endl;

    // Assign the same lambda expression to a function object.
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };

    cout << f2(3, 4) << endl;
}
```

### <a name="output"></a>Çıkış

```Output
5
7
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [otomatik](../cpp/auto-cpp.md), [sınıf işlev](../standard-library/function-class.md), ve [işlevi çağrısı](../cpp/function-call-cpp.md).

Lambda ifadeleri bir işlev gövdesinde çoğunlukla bildirilse bunları herhangi bir yerde bir değişkeni başlatabileceğiniz bildirebilirsiniz.

### <a name="example-2"></a>Örnek 2

Visual C++ derleyicisi, ifade çağrıldığında değil de bildirildiğinde yakalanan değişkenlerine bir lambda ifadesi bağlar. Aşağıdaki örnek, yerel değişken yakalayan bir lambda ifadesi gösterir `i` değere göre ve yerel değişken `j` başvuruya göre. Lambda ifadesi `i` değeriyle yeniden atanması `i` programda daha sonra ifadenin sonucunu etkilemez. Ancak, lambda ifadesi `j` başvuruyla yeniden atanması `j` ifadenin sonucunu etkilemez.

### <a name="code"></a>Kod

```cpp
// declaring_lambda_expressions2.cpp
// compile with: /EHsc /W4
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   int i = 3;
   int j = 5;

   // The following lambda expression captures i by value and
   // j by reference.
   function<int (void)> f = [i, &j] { return i + j; };

   // Change the values of i and j.
   i = 22;
   j = 44;

   // Call f and print its result.
   cout << f() << endl;
}
```

### <a name="output"></a>Çıkış

```Output
47
```

[[Bu makaledeki](#top)]

##  <a name="callingLambdaExpressions"></a> Lambda ifadeleri çağırma

Bir lambda ifadeyi sonraki kod parçacığında gösterildiği gibi anında çağırabilirsiniz. İkinci kod parçacığı gibi standart C++ Kitaplığı algoritmaları için bir lambda bağımsız değişken olarak geçirmek gösterilmektedir `find_if`.

### <a name="example-1"></a>Örnek 1

Bu örnek iki tam sayının toplamını döndürür ve ifade bağımsız değişkenleriyle anında çağıran bir lambda ifadesi bildirir `5` ve `4`:

### <a name="code"></a>Kod

```cpp
// calling_lambda_expressions1.cpp
// compile with: /EHsc
#include <iostream>

int main()
{
   using namespace std;
   int n = [] (int x, int y) { return x + y; }(5, 4);
   cout << n << endl;
}
```

### <a name="output"></a>Çıkış

```Output
9
```

### <a name="example-2"></a>Örnek 2

Bu örnekte bir lambda ifadesi bağımsız değişkeni olarak geçirir. `find_if` işlevi. Lambda ifadesi döndürür **true** , parametresinin bir çift sayı ise.

### <a name="code"></a>Kod

```cpp
// calling_lambda_expressions2.cpp
// compile with: /EHsc /W4
#include <list>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;

    // Create a list of integers with a few initial elements.
    list<int> numbers;
    numbers.push_back(13);
    numbers.push_back(17);
    numbers.push_back(42);
    numbers.push_back(46);
    numbers.push_back(99);

    // Use the find_if function and a lambda expression to find the
    // first even number in the list.
    const list<int>::const_iterator result =
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });

    // Print the result.
    if (result != numbers.end()) {
        cout << "The first even number in the list is " << *result << "." << endl;
    } else {
        cout << "The list contains no even numbers." << endl;
    }
}
```

### <a name="output"></a>Çıkış

```Output
The first even number in the list is 42.
```

### <a name="remarks"></a>Açıklamalar

Hakkında daha fazla bilgi için `find_if` çalışması için bkz: [find_if](../standard-library/algorithm-functions.md#find_if). Yaygın algoritmalar gerçekleştiren standart C++ Kitaplığı işlevleri hakkında daha fazla bilgi için bkz: [ \<algoritma >](../standard-library/algorithm.md).

[[Bu makaledeki](#top)]

##  <a name="nestingLambdaExpressions"></a> Lambda ifadeleri iç içe geçirme

### <a name="example"></a>Örnek

Bu örnekte gösterildiği gibi, bir lambda ifadeyi başka bir tanesinin içine yerleştirebilirsiniz. İç lambda ifadesi bağımsız değişkenini 2 ile çarpar ve sonucu döndürür. Dış lambda ifadesi bağımsız değişkeni ile iç lambda ifadesini çağırır ve sonuca 3 ekler.

### <a name="code"></a>Kod

```cpp
// nesting_lambda_expressions.cpp
// compile with: /EHsc /W4
#include <iostream>

int main()
{
    using namespace std;

    // The following lambda expression contains a nested lambda
    // expression.
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);

    // Print the result.
    cout << timestwoplusthree << endl;
}
```

### <a name="output"></a>Çıkış

```Output
13
```

### <a name="remarks"></a>Açıklamalar

Bu örnekte, `[](int y) { return y * 2; }` iç içe geçmiş lambda ifadesidir.

[[Bu makaledeki](#top)]

##  <a name="higherOrderLambdaExpressions"></a> Daha yüksek sıralı Lambda işlevleri

### <a name="example"></a>Örnek

Birçok programlama dili kavramını destekler. bir *yüksek sıralı işlev.* Yüksek sıralı işlev, başka bir lambda ifadesini kendi bağımsız değişkeni olarak alan veya döndüren bir lambda ifadesidir. Kullanabileceğiniz [işlevi](../standard-library/function-class.md) davranacak şekilde bir C++ lambda ifadesinin etkinleştirmek için sınıf gibi yüksek sıralı işlev. Aşağıdaki örnek, döndüren bir lambda ifadesi gösterir. bir `function` nesne ve alan bir lambda ifadesi bir `function` ve bağımsız değişkeni olarak.

### <a name="code"></a>Kod

```cpp
// higher_order_lambda_expression.cpp
// compile with: /EHsc /W4
#include <iostream>
#include <functional>

int main()
{
    using namespace std;

    // The following code declares a lambda expression that returns
    // another lambda expression that adds two numbers.
    // The returned lambda expression captures parameter x by value.
    auto addtwointegers = [](int x) -> function<int(int)> {
        return [=](int y) { return x + y; };
    };

    // The following code declares a lambda expression that takes another
    // lambda expression as its argument.
    // The lambda expression applies the argument z to the function f
    // and multiplies by 2.
    auto higherorder = [](const function<int(int)>& f, int z) {
        return f(z) * 2;
    };

    // Call the lambda expression that is bound to higherorder.
    auto answer = higherorder(addtwointegers(7), 8);

    // Print the result, which is (7+8)*2.
    cout << answer << endl;
}
```

### <a name="output"></a>Çıkış

```Output
30
```

[[Bu makaledeki](#top)]

##  <a name="methodLambdaExpressions"></a> Bir işlevde bir Lambda ifadesini kullanma

### <a name="example"></a>Örnek

Bir işlevin gövdesinde lambda ifadeleri kullanabilirsiniz. Lambda ifadesi, kapsayan işlevin erişip herhangi bir işlev veya veri üyesi erişebilir. Açıkça veya dolaylı olarak yakalayabilirsiniz **bu** işlevleri ve verileri kapsayan sınıfın üyelerine erişim sağlamak için işaretçi.
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Yakalama **bu** değeriyle (`[*this]`) ne zaman lambda kullanılacak paralel veya zaman uyumsuz işlemleri özgün nesne kapsam dışına geçtikten sonra kod burada paralellikle çalışabilir.

Kullanabileceğiniz **bu** burada gösterildiği gibi açıkça bir işlevde işaretçi:

```cpp
// capture "this" by reference
void ApplyScale(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [this](int n) { cout << n * _scale << endl; });
}

// capture "this" by value (Visual Studio 2017 version 15.3 and later)
void ApplyScale2(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [*this](int n) { cout << n * _scale << endl; });
}
```

Ayrıca yakalayabilirsiniz **bu** işaretçi örtük olarak:

```cpp
void ApplyScale(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [=](int n) { cout << n * _scale << endl; });
}
```

Aşağıdaki örnekte gösterildiği `Scale` bir ölçek değer kapsülleyen sınıfı.

```cpp
// function_lambda_expression.cpp
// compile with: /EHsc /W4
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

class Scale
{
public:
    // The constructor.
    explicit Scale(int scale) : _scale(scale) {}

    // Prints the product of each element in a vector object
    // and the scale value to the console.
    void ApplyScale(const vector<int>& v) const
    {
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });
    }

private:
    int _scale;
};

int main()
{
    vector<int> values;
    values.push_back(1);
    values.push_back(2);
    values.push_back(3);
    values.push_back(4);

    // Create a Scale object that scales elements by 3 and apply
    // it to the vector object. Does not modify the vector.
    Scale s(3);
    s.ApplyScale(values);
}
```

### <a name="output"></a>Çıkış

```Output
3
6
9
12
```

### <a name="remarks"></a>Açıklamalar

`ApplyScale` İşlevi ölçek değeri ve her öğenin çarpımını yazdırmak için bir lambda ifadesi kullanır bir `vector` nesne. Lambda ifadesi örtük olarak yakalayan **bu** erişebilmesi için `_scale` üyesi.

[[Bu makaledeki](#top)]

##  <a name="templateLambdaExpressions"></a> Lambda ifadelerini şablonlarla kullanma

### <a name="example"></a>Örnek

Lambda ifadeleri yazıldığından, bunları C++ şablonlarıyla birlikte kullanabilirsiniz. Aşağıdaki örnekte gösterildiği `negate_all` ve `print_all` işlevleri. `negate_all` İşlevi uygular birli **operator -** içindeki her öğeyi `vector` nesne. `print_all` İşlevi her öğedeki yazdırır `vector` konsola nesne.

### <a name="code"></a>Kod

```cpp
// template_lambda_expression.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

using namespace std;

// Negates each element in the vector object. Assumes signed data type.
template <typename T>
void negate_all(vector<T>& v)
{
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });
}

// Prints to the console each element in the vector object.
template <typename T>
void print_all(const vector<T>& v)
{
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });
}

int main()
{
    // Create a vector of signed integers with a few elements.
    vector<int> v;
    v.push_back(34);
    v.push_back(-43);
    v.push_back(56);

    print_all(v);
    negate_all(v);
    cout << "After negate_all():" << endl;
    print_all(v);
}
```

### <a name="output"></a>Çıkış

```Output
34
-43
56
After negate_all():
-34
43
-56
```

### <a name="remarks"></a>Açıklamalar

C++ şablonları hakkında daha fazla bilgi için bkz. [şablonları](../cpp/templates-cpp.md).

[[Bu makaledeki](#top)]

##  <a name="ehLambdaExpressions"></a> Özel durumları işleme

### <a name="example"></a>Örnek

Bir lambda ifadesinin gövdesi, hem yapısal özel durum işleme (SEH) hem de C++ özel durum işleme kurallarına uyar. Harekete geçirilmiş bir özel bir durumu, lambda ifadesinin gövdesi içinde işleyebilir veya özel durum işlemesini kapsayan kapsama erteleyebilirsiniz. Aşağıdaki örnekte **for_each** işlevi ve doldurmak için bir lambda ifadesi bir `vector` değerleriyle başka bir nesne. Bunu kullanan bir **deneyin**/**catch** ilk vektöre geçersiz erişimi işlemek için blok.

### <a name="code"></a>Kod

```cpp
// eh_lambda_expression.cpp
// compile with: /EHsc /W4
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

int main()
{
    // Create a vector that contains 3 elements.
    vector<int> elements(3);

    // Create another vector that contains index values.
    vector<int> indices(3);
    indices[0] = 0;
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.
    indices[2] = 2;

    // Use the values from the vector of index values to
    // fill the elements vector. This example uses a
    // try/catch block to handle invalid access to the
    // elements vector.
    try
    {
        for_each(indices.begin(), indices.end(), [&](int index) {
            elements.at(index) = index;
        });
    }
    catch (const out_of_range& e)
    {
        cerr << "Caught '" << e.what() << "'." << endl;
    };
}
```

### <a name="output"></a>Çıkış

```Output
Caught 'invalid vector<T> subscript'.
```

### <a name="remarks"></a>Açıklamalar

Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md).

[[Bu makaledeki](#top)]

##  <a name="managedLambdaExpressions"></a> Yönetilen türler ile lambda ifadeleri kullanma (C++/CLI)

### <a name="example"></a>Örnek

Bir lambda ifadesinin yakalama yan tümcesi yönetilen bir türe sahip bir değişken içeremez. Ancak, lambda ifadesi parametre listesine, yönetilen bir türe sahip bir bağımsız değişken geçirebilirsiniz. Aşağıdaki örnek yerel Yönetilmemiş değişken yakalayan bir lambda ifadesi içerir `ch` değere göre ve gerçekleştirilen işlemlerin bir <xref:System.String?displayProperty=fullName> parametre olarak nesne.

### <a name="code"></a>Kod

```cpp
// managed_lambda_expression.cpp
// compile with: /clr
using namespace System;

int main()
{
    char ch = '!'; // a local unmanaged variable

    // The following lambda expression captures local variables
    // by value and takes a managed String object as its parameter.
    [=](String ^s) {
        Console::WriteLine(s + Convert::ToChar(ch));
    }("Hello");
}
```

### <a name="output"></a>Çıkış

```Output
Hello!
```

### <a name="remarks"></a>Açıklamalar

STL/CLR kitaplığı ile lambda ifadeleri de kullanabilirsiniz. Daha fazla bilgi için [STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md).

> [!IMPORTANT]
>  Lambdalar bu ortak dil çalışma zamanı (CLR) yönetilen varlıklar içinde desteklenmiyor: **başvuru sınıfı**, **ref struct**, **değer sınıfının**, ve **değeryapısı**.

[[Bu makaledeki](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda İfadesi Söz Dizimi](../cpp/lambda-expression-syntax.md)<br/>
[auto](../cpp/auto-cpp.md)<br/>
[function Sınıfı](../standard-library/function-class.md)<br/>
[find_if](../standard-library/algorithm-functions.md#find_if)<br/>
[\<algoritma >](../standard-library/algorithm.md)<br/>
[İşlev Çağrısı](../cpp/function-call-cpp.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)