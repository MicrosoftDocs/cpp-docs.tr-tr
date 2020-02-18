---
title: Hata Ayıklama Yineleyicisi Desteği
ms.date: 09/13/2018
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
- C++ Standard Library, debug iterator support
- iterators, debug iterator support
- iterators, incompatible
- incompatible iterators
- debug iterator support
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
ms.openlocfilehash: f43367fd58d8ab2a62fb2312efcd9fc9ec0cfc42
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416198"
---
# <a name="debug-iterator-support"></a>Hata Ayıklama Yineleyicisi Desteği

Görsel C++ çalışma zamanı kitaplığı yanlış yineleyici kullanımını algılar ve çalışma zamanında bir iletişim kutusu görüntüler. Hata ayıklama Yineleyici desteğini etkinleştirmek için, programınızı derlemek için C++ standart kitaplığın ve C çalışma zamanı kitaplığının hata ayıklama sürümlerini kullanmanız gerekir. Daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md). Denetlenen yineleyiciler kullanma hakkında daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

Standart C++ , üye işlevlerinin kapsayıcı için yineleyicilerin geçersiz hale gelmesine neden olabileceğini açıklar. İki örnek şunlardır:

- Bir kapsayıcıdan öğe silme, öğe için yineleyiciler geçersiz hale gelmesine neden olur.

- İtme veya ekleme kullanarak bir [Vector](../standard-library/vector.md) boyutunu artırmak `vector` yineleyiciler geçersiz hale gelir.

## <a name="invalid-iterators"></a>Geçersiz Yineleyiciler

Bu örnek programı hata ayıklama modunda derlerseniz, çalışma zamanında onaylar ve sonlanır.

```cpp
// iterator_debugging_0.cpp
// compile by using /EHsc /MDd
#include <vector>
#include <iostream>

int main() {
   std::vector<int> v {10, 15, 20};
   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

## <a name="using-_iterator_debug_level"></a>_ITERATOR_DEBUG_LEVEL kullanma

Bir hata ayıklama derlemesinde Yineleyici hata ayıklama özelliğini kapatmak için önişlemci makrosunu [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanabilirsiniz. Bu program onaylama işlemi yapmaz, ancak yine de tanımsız davranışı tetikler.

```cpp
// iterator_debugging_1.cpp
// compile by using: /EHsc /MDd
#define _ITERATOR_DEBUG_LEVEL 0
#include <vector>
#include <iostream>

int main() {
    std::vector<int> v {10, 15, 20};

   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

```Output
20
-572662307
```

## <a name="unitialized-iterators"></a>Açılmamış yineleyiciler

Burada gösterildiği gibi, bir yineleyici kullanılmadan önce bir yineleyici kullanmayı denerseniz bir onaylama da oluşur:

```cpp
// iterator_debugging_2.cpp
// compile by using: /EHsc /MDd
#include <string>
using namespace std;

int main() {
   string::iterator i1, i2;
   if (i1 == i2)
      ;
}
```

## <a name="incompatible-iterators"></a>Uyumsuz yineleyiciler

Aşağıdaki kod örneği bir onaylama işlemi oluşmasına neden olur çünkü [for_each](../standard-library/algorithm-functions.md#for_each) algoritmasındaki iki yineleyiciler uyumsuz. Algoritmalar, kendisine sağlanan yineleyicilerin aynı kapsayıcıya başvurmalarını sağlamak için kontrol edilir.

```cpp
// iterator_debugging_3.cpp
// compile by using /EHsc /MDd
#include <algorithm>
#include <vector>
using namespace std;

int main()
{
    vector<int> v1 {10, 20};
    vector<int> v2 {10, 20};

    // The next line asserts because v1 and v2 are
    // incompatible.
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );
}
```

Bu örnekte, bir functor yerine `[] (int& elem) { elem *= 2; }` lambda ifadesini kullandığına dikkat edin. Bu seçeneğin onaylama hatası üzerinde hiçbir ilgisi yoktur, ancak benzer bir komik ctor aynı hataya neden olur — Lambdalar, Compact Function nesne görevlerini gerçekleştirmek için çok faydalı bir yoldur. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="iterators-going-out-of-scope"></a>Kapsam dışına çıkan yineleyiciler

Ayrıca, **for** döngüsü kapsamı sona erdiğinde, **for** döngüsünde belirtilen bir yineleyici değişkeninin kapsam dışına alınmasına neden olan hata ayıklama Yineleyici denetimleri.

```cpp
// iterator_debugging_4.cpp
// compile by using: /EHsc /MDd
#include <vector>
#include <iostream>
int main() {
   std::vector<int> v {10, 15, 20};

   for (std::vector<int>::iterator i = v.begin(); i != v.end(); ++i)
      ;   // do nothing
   --i;   // C2065
}
```

## <a name="destructors-for-debug-iterators"></a>Hata ayıklama yineleyiciler için Yıkıcılar

Hata ayıklama yineleyiciler önemsiz olmayan yıkıcıya sahip. Yıkıcı çalıştırılmadığında ancak nesnenin belleği serbest bırakılırsa, erişim ihlalleri ve veri bozulması meydana gelebilir. Şu örneği göz önünde bulundurun:

```cpp
// iterator_debugging_5.cpp
// compile by using: /EHsc /MDd
#include <vector>
struct base {
   // TO FIX: uncomment the next line
   // virtual ~base() {}
};

struct derived : base {
   std::vector<int>::iterator m_iter;
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}
   ~derived() {}
};

int main() {
   std::vector<int> vect( 10 );
   base * pb = new derived( vect.begin() );
   delete pb;  // doesn't call ~derived()
   // access violation
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)
