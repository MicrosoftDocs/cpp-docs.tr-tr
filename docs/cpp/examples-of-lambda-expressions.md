---
title: Lambda İfadeleri Örnekleri
ms.date: 05/07/2019
helpviewer_keywords:
- lambda expressions [C++], examples
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
ms.openlocfilehash: 585e76119b0e848e322c88ad0149ebb42c6b5b1d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221607"
---
# <a name="examples-of-lambda-expressions"></a>Lambda İfadeleri Örnekleri

Bu makalede, lambda ifadelerinin programlarınızda nasıl kullanılacağı gösterilmektedir. Lambda ifadelerine genel bakış için bkz. [lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md). Lambda ifadesinin yapısı hakkında daha fazla bilgi için bkz. [lambda Ifadesi sözdizimi](../cpp/lambda-expression-syntax.md).

## <a name="declaring-lambda-expressions"></a><a name="declaringLambdaExpressions"></a>Lambda Ifadelerini bildirme

### <a name="example-1"></a>Örnek 1

Bir lambda ifadesi yazıldığı için, **`auto`** [`function`](../standard-library/function-class.md) burada gösterildiği gibi bir değişkene veya nesnesine atayabilirsiniz:

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

### <a name="output"></a>Çıktı

```Output
5
7
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz [`auto`](../cpp/auto-cpp.md) ., [ `function` sınıf](../standard-library/function-class.md)ve [işlev çağrısı](../cpp/function-call-cpp.md).

Lambda ifadeleri çoğu zaman bir işlevin gövdesinde bildirilmesine rağmen, bunları bir değişken başlatabileceğiniz her yerde bildirebilirsiniz.

### <a name="example-2"></a>Örnek 2

Microsoft C++ derleyicisi, ifade çağrıldığında bir lambda ifadesini yakalanan değişkenlere bağlar. Aşağıdaki örnek, yerel değişkeni `i` değere göre ve yerel değişkeni başvuruya göre yakalayan bir lambda ifadesi gösterir `j` . Lambda ifadesi değere göre yakaladığı için `i` , `i` daha sonra programda yeniden atama ifadenin sonucunu etkilemez. Ancak, lambda ifadesi başvuruya göre yakaladığı için `j` , öğesinin yeniden atanması `j` ifadenin sonucunu etkiler.

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

### <a name="output"></a>Çıktı

```Output
47
```

[[Bu makalede](#top)]

## <a name="calling-lambda-expressions"></a><a name="callingLambdaExpressions"></a>Lambda Ifadeleri çağırma

Bir lambda ifadeyi sonraki kod parçacığında gösterildiği gibi anında çağırabilirsiniz. İkinci kod parçacığı, bir lambda gibi C++ standart kitaplık algoritmalarına bağımsız değişken olarak nasıl geçirileceğini gösterir `find_if` .

### <a name="example-1"></a>Örnek 1

Bu örnek, iki tamsayının toplamını döndüren bir lambda ifadesi bildirir ve ifadeyi bağımsız değişkenlerle hemen çağırır `5` `4` :

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

### <a name="output"></a>Çıktı

```Output
9
```

### <a name="example-2"></a>Örnek 2

Bu örnek, bir lambda ifadesini işlevine bağımsız değişken olarak geçirir `find_if` . Lambda ifadesi, **`true`** parametresi çift sayı ise döndürür.

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

### <a name="output"></a>Çıktı

```Output
The first even number in the list is 42.
```

### <a name="remarks"></a>Açıklamalar

İşlevi hakkında daha fazla bilgi için `find_if` bkz [`find_if`](../standard-library/algorithm-functions.md#find_if) .. Ortak algoritmaları gerçekleştiren C++ standart kitaplığı işlevleri hakkında daha fazla bilgi için bkz [`<algorithm>`](../standard-library/algorithm.md) ..

[[Bu makalede](#top)]

## <a name="nesting-lambda-expressions"></a><a name="nestingLambdaExpressions"></a>Lambda Ifadeleri iç içe geçme

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

### <a name="output"></a>Çıktı

```Output
13
```

### <a name="remarks"></a>Açıklamalar

Bu örnekte, `[](int y) { return y * 2; }` iç içe lambda ifadesi olur.

[[Bu makalede](#top)]

## <a name="higher-order-lambda-functions"></a><a name="higherOrderLambdaExpressions"></a>Daha yüksek sıralı Lambda Işlevleri

### <a name="example"></a>Örnek

Birçok programlama dili, *daha yüksek sıralı bir işlev* kavramını destekler. Yüksek sıralı işlev, başka bir lambda ifadesini kendi bağımsız değişkeni olarak alan veya döndüren bir lambda ifadesidir. [`function`](../standard-library/function-class.md)Sınıfını, bir C++ lambda ifadesinin daha yüksek sıralı bir işlev gibi davranmasını sağlamak için kullanabilirsiniz. Aşağıdaki örnek, bir nesnesi `function` ve bağımsız değişkeni olarak bir nesnesi alan bir lambda ifadesi döndüren bir lambda ifadesini gösterir `function` .

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

### <a name="output"></a>Çıktı

```Output
30
```

[[Bu makalede](#top)]

## <a name="using-a-lambda-expression-in-a-function"></a><a name="methodLambdaExpressions"></a>Bir Işlevde lambda Ifadesi kullanma

### <a name="example"></a>Örnek

Bir işlevin gövdesinde lambda ifadeleri kullanabilirsiniz. Lambda ifadesi, kapsayan işlevin erişebileceği herhangi bir işleve veya veri üyesine erişebilir. **`this`** Kapsayan sınıfın işlevlerine ve veri üyelerine erişim sağlamak için işaretçiyi açıkça veya dolaylı olarak yakalayabilirsiniz.
**Visual Studio 2017 sürüm 15,3 ve üzeri** (ile kullanılabilir [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`this`** lambda, `[*this]` özgün nesne kapsam dışına çıktıktan sonra, kodun yürütebileceği zaman uyumsuz veya paralel işlemlerde kullanılacak, değere göre yakala ().

**`this`** İşaretçiyi, burada gösterildiği gibi açıkça bir işlevde kullanabilirsiniz:

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

Ayrıca işaretçiyi örtük bir şekilde yakalayabilirsiniz **`this`** :

```cpp
void ApplyScale(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [=](int n) { cout << n * _scale << endl; });
}
```

Aşağıdaki örnek, `Scale` bir ölçek değerini kapsülleyen sınıfını gösterir.

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

### <a name="output"></a>Çıktı

```Output
3
6
9
12
```

### <a name="remarks"></a>Açıklamalar

`ApplyScale`İşlevi, ölçek değerinin çarpımını ve bir nesnedeki her öğeyi yazdırmak için bir lambda ifadesi kullanır `vector` . Lambda ifadesi, üyeye erişmek için örtülü olarak yakalar **`this`** `_scale` .

[[Bu makalede](#top)]

## <a name="using-lambda-expressions-with-templates"></a><a name="templateLambdaExpressions"></a>Şablonlarla lambda Ifadeleri kullanma

### <a name="example"></a>Örnek

Lambda ifadeleri yazıldığından, bunları C++ şablonlarıyla birlikte kullanabilirsiniz. Aşağıdaki örnekte `negate_all` ve `print_all` işlevleri gösterilmektedir. `negate_all`İşlev, birli **`operator-`** öğeyi nesnesindeki her öğeye uygular `vector` . `print_all`İşlevi, nesnesindeki her öğeyi konsola yazdırır `vector` .

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

### <a name="output"></a>Çıktı

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

C++ şablonları hakkında daha fazla bilgi için bkz. [Şablonlar](../cpp/templates-cpp.md).

[[Bu makalede](#top)]

## <a name="handling-exceptions"></a><a name="ehLambdaExpressions"></a>Özel durumları işleme

### <a name="example"></a>Örnek

Bir lambda ifadesinin gövdesi, hem yapısal özel durum işleme (SEH) hem de C++ özel durum işleme kurallarına uyar. Harekete geçirilmiş bir özel bir durumu, lambda ifadesinin gövdesi içinde işleyebilir veya özel durum işlemesini kapsayan kapsama erteleyebilirsiniz. Aşağıdaki örnek, bir **`for_each`** nesneyi başka bir değer ile doldurmanız için işlevini ve bir lambda ifadesini kullanır `vector` . **`try`** / **`catch`** İlk vektöre geçersiz erişimi işlemek için bir blok kullanır.

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

### <a name="output"></a>Çıktı

```Output
Caught 'invalid vector<T> subscript'.
```

### <a name="remarks"></a>Açıklamalar

Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md).

[[Bu makalede](#top)]

## <a name="using-lambda-expressions-with-managed-types-ccli"></a><a name="managedLambdaExpressions"></a>Yönetilen türlerle lambda Ifadeleri kullanma (C++/CLı)

### <a name="example"></a>Örnek

Bir lambda ifadesinin yakalama yan tümcesi yönetilen bir türe sahip bir değişken içeremez. Ancak, lambda ifadesi parametre listesine, yönetilen bir türe sahip bir bağımsız değişken geçirebilirsiniz. Aşağıdaki örnek, yerel yönetilmeyen değişkeni değere göre yakalayan bir lambda ifadesi içerir `ch` ve bir <xref:System.String?displayProperty=fullName> nesneyi parametresi olarak alır.

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

### <a name="output"></a>Çıktı

```Output
Hello!
```

### <a name="remarks"></a>Açıklamalar

STL/CLR kitaplığı ile lambda ifadeleri de kullanabilirsiniz. Daha fazla bilgi için bkz. [STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md).

> [!IMPORTANT]
> Lambdalar şu ortak dil çalışma zamanı (CLR) yönetilen varlıklarda desteklenmez: **`ref class`** , **`ref struct`** , **`value class`** ve **`value struct`** .

[[Bu makalede](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda Ifadesi söz dizimi](../cpp/lambda-expression-syntax.md)<br/>
[`auto`](../cpp/auto-cpp.md)<br/>
[`function`Sınıfı](../standard-library/function-class.md)<br/>
[`find_if`](../standard-library/algorithm-functions.md#find_if)<br/>
[`<algorithm>`](../standard-library/algorithm.md)<br/>
[İşlev çağrısı](../cpp/function-call-cpp.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md)
