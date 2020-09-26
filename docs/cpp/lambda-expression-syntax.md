---
title: Lambda İfadesi Sözdizimi
ms.date: 05/07/2019
helpviewer_keywords:
- lambda expressions [C++], syntax
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
ms.openlocfilehash: 8db094dd14e63c08fbe8514f245c1777922224cf
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352719"
---
# <a name="lambda-expression-syntax"></a>Lambda İfadesi Sözdizimi

Bu makalede lambda ifadelerinin sözdizimi ve yapısal öğeleri gösterilmektedir. Lambda ifadelerinin açıklaması için bkz. [lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="function-objects-vs-lambdas"></a>İşlev Nesneleri ile Lambdaların Karşılaştırılması

Kod yazdığınızda, özellikle de [C++ Standart Kitaplığı algoritmaları](../standard-library/algorithms.md)kullandığınızda sorunları çözümlemek ve hesaplamalar gerçekleştirmek için işlev işaretçilerini ve işlev nesnelerini kullanırsınız. İşlev işaretçilerinin ve işlev nesnelerinin avantajları ve dezavantajları vardır. Örneğin, işlev işaretçileri en az sözdizimsel yüke sahiptir ancak bir kapsamda durumu korumaz ve işlev nesneleri durum saklayabilir, ancak bir sınıf tanımının sözdizimsel ek yükünü gerektirir.

Bir lambda, işlev işaretçilerinin ve işlev nesnelerinin avantajlarını bir araya getirirken dezavantajlarını ortadan kaldırır. İşlev nesneleri gibi bir lambda esnektir ve durumu koruyabilir, ancak bir işlev nesnesinden farklı olarak, Compact sözdizimi açık bir sınıf tanımı gerektirmez. Lambdaları kullanarak, bir işlev nesnesine eşdeğer koda göre daha az hantal ve hataya daha az eğilimli kod yazabilirsiniz.

Aşağıdaki örnekler, lambda kullanımını işlevi nesnesi kullanımıyla karşılaştırır. İlk örnek, bir nesnedeki her öğenin çift veya tek olup olmadığı konsola yazdırmak için bir lambda kullanır `vector` . İkinci örnek aynı görevi başarmak için bir işlev nesnesi kullanır.

## <a name="example-1-using-a-lambda"></a>Örnek 1: Bir Lambda Kullanma

Bu örnek **for_each** işlevine bir lambda geçirir. Lambda, bir nesnedeki her öğenin çift mi yoksa tek mi olduğunu belirten bir sonuç yazdırır `vector` .

### <a name="code"></a>Kod

```cpp
// even_lambda.cpp
// compile with: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
   // Create a vector object that contains 9 elements.
   vector<int> v;
   for (int i = 1; i < 10; ++i) {
      v.push_back(i);
   }

   // Count the number of even numbers in the vector by
   // using the for_each function and a lambda.
   int evenCount = 0;
   for_each(v.begin(), v.end(), [&evenCount] (int n) {
      cout << n;
      if (n % 2 == 0) {
         cout << " is even " << endl;
         ++evenCount;
      } else {
         cout << " is odd " << endl;
      }
   });

   // Print the count of even numbers to the console.
   cout << "There are " << evenCount
        << " even numbers in the vector." << endl;
}
```

```Output
1 is odd
2 is even
3 is odd
4 is even
5 is odd
6 is even
7 is odd
8 is even
9 is odd
There are 4 even numbers in the vector.
```

### <a name="comments"></a>Yorumlar

Örnekte, **for_each** işlevinin üçüncü bağımsız değişkeni bir lambda 'dir. `[&evenCount]`Bölüm, ifadenin yakalama yan tümcesini belirtir, `(int n)` parametre listesini belirtir ve kalan bölüm, ifadenin gövdesini belirtir.

## <a name="example-2-using-a-function-object"></a>Örnek 2: Bir İşlev Nesnesi Kullanma

Bazen bir lambda önceki örnekten daha fazla genişletmek için çok kullanışsız olur. Sonraki örnek, örnek 1 ile aynı sonuçları üretmek için **for_each** işleviyle birlikte lambda yerine bir işlev nesnesi kullanır. Her iki örnek de bir nesne içindeki çift sayı sayısını depolar `vector` . İşlemin durumunu korumak için, `FunctorClass` sınıfı `m_evenCount` değişkeni bir üye değişkeni olarak başvuruya göre depolar. İşlemi gerçekleştirmek için, `FunctorClass` **işleç ()** işlev çağrısı işlecini uygular. Microsoft C++ derleyicisi, örnek 1 ' deki lambda koduna boyut ve performansa benzer bir kod üretir. Bu makaledeki gibi temel bir sorun için, daha basit bir lambda tasarımı işlev nesnesi tasarımından genellikle daha iyi bir tasarımdır. Ancak ilerde işlevsellik için önemli bir genişletme gerekeceğini düşünüyorsanız, kodu korumayı kolaylaştıracak işlev nesnesi tasarımını kullanabilirsiniz.

**İşleci ()** hakkında daha fazla bilgi için bkz. [işlev çağrısı](../cpp/function-call-cpp.md). **For_each** işlevi hakkında daha fazla bilgi için bkz. [for_each](../standard-library/algorithm-functions.md#for_each).

### <a name="code"></a>Kod

```cpp
// even_functor.cpp
// compile with: /EHsc
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

class FunctorClass
{
public:
    // The required constructor for this example.
    explicit FunctorClass(int& evenCount)
        : m_evenCount(evenCount) { }

    // The function-call operator prints whether the number is
    // even or odd. If the number is even, this method updates
    // the counter.
    void operator()(int n) const {
        cout << n;

        if (n % 2 == 0) {
            cout << " is even " << endl;
            ++m_evenCount;
        } else {
            cout << " is odd " << endl;
        }
    }

private:
    // Default assignment operator to silence warning C4512.
    FunctorClass& operator=(const FunctorClass&);

    int& m_evenCount; // the number of even variables in the vector.
};

int main()
{
    // Create a vector object that contains 9 elements.
    vector<int> v;
    for (int i = 1; i < 10; ++i) {
        v.push_back(i);
    }

    // Count the number of even numbers in the vector by
    // using the for_each function and a function object.
    int evenCount = 0;
    for_each(v.begin(), v.end(), FunctorClass(evenCount));

    // Print the count of even numbers to the console.
    cout << "There are " << evenCount
        << " even numbers in the vector." << endl;
}
```

```Output
1 is odd
2 is even
3 is odd
4 is even
5 is odd
6 is even
7 is odd
8 is even
9 is odd
There are 4 even numbers in the vector.
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda Ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md)<br/>
[üretecek](../standard-library/algorithm-functions.md#generate)<br/>
[generate_n](../standard-library/algorithm-functions.md#generate_n)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)<br/>
[Özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md)<br/>
[Derleyici Uyarısı (düzey 1) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)<br/>
[Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md)
