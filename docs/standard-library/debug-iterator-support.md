---
title: Hata ayıklama yineleyici desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
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
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0e5677259df65383eddc474d2b26d15e024776b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="debug-iterator-support"></a>Hata Ayıklama Yineleyicisi Desteği

Visual C++ çalışma zamanı kitaplığı yanlış yineleyici kullanım algılar ve onaylar ve çalışma zamanında bir iletişim kutusu görüntüler. Hata ayıklama yineleyici desteği etkinleştirmek için program derlemek için hata ayıklama sürümleri C++ Standart Kitaplığı ve C çalışma zamanı kitaplığı kullanmanız gerekir. Daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md). İşaretli yineleyiciler kullanma hakkında daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).

Standart C++ üye işlevlerini geçersiz hale yineleyiciler bir kapsayıcıya nasıl neden olabilecek açıklar. İki örnek verilmiştir:

- Bir kapsayıcı bir öğeyi silme yineleyiciler öğesine geçersiz hale gelmesine neden olur.

- Boyutunu artırma bir [vektör](../standard-library/vector.md) kullanarak anında iletme veya nedenler yineleyiciler içine INSERT `vector` geçersiz olacak.

## <a name="example"></a>Örnek

Bu örnek program hata ayıklama modunda derleme değilse, çalışma zamanında onaylar ve sonlandırır.

```cpp
// iterator_debugging_0.cpp
// compile by using /EHsc /MDd
#include <vector>
#include <iostream>

int main() {
   std::vector<int> v ;

   v.push_back(10);
   v.push_back(15);
   v.push_back(20);

   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

## <a name="example"></a>Örnek

Önişlemci makrosu kullanabilirsiniz [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) hata ayıklama derlemesi özelliğinde hata ayıklama yineleyici devre dışı bırakmak için. Bu program assert değil, ancak hala tanımsız davranışı tetikler.

```cpp
// iterator_debugging_1.cpp
// compile by using: /EHsc /MDd
#define _ITERATOR_DEBUG_LEVEL 0
#include <vector>
#include <iostream>

int main() {
   std::vector<int> v ;

   v.push_back(10);
   v.push_back(15);
   v.push_back(20);

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

## <a name="example"></a>Örnek

Assert başlatılmadan, aşağıda gösterildiği gibi yineleyici kullanmayı denerseniz, ayrıca oluşur:

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

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde bir onaylama neden olur iki yineleyiciler [for_each](../standard-library/algorithm-functions.md#for_each) algoritması uyumsuz. Kendilerine sağlanan yineleyiciler aynı kapsayıcı başvuru olup olmadığını belirlemek için algoritmaları denetleyin.

```cpp
// iterator_debugging_3.cpp
// compile by using /EHsc /MDd
#include <algorithm>
#include <vector>
using namespace std;

int main()
{
    vector<int> v1;
    vector<int> v2;

    v1.push_back(10);
    v1.push_back(20);

    v2.push_back(10);
    v2.push_back(20);

    // The next line asserts because v1 and v2 are
    // incompatible.
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );
}
```

Bu örnek lambda ifadesi kullanır bildirimi `[] (int& elem) { elem *= 2; }` bir functor yerine. Bu seçenek şifrelemeyle assert Kuramama olsa — benzer functor aynı başarısız olmasına neden — Lambda'lar olan compact işlevi nesne görevleri gerçekleştirmek için çok kullanışlı bir yol. Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="example"></a>Örnek

Hata ayıklama yineleyici denetimleri de içinde bildirilen bir yineleyici değişkeni neden bir `for` döngü dışında olması için ne zaman kapsam `for` kapsam uçları döngü.

```cpp
// iterator_debugging_4.cpp
// compile by using: /EHsc /MDd
#include <vector>
#include <iostream>
int main() {
   std::vector<int> v ;

   v.push_back(10);
   v.push_back(15);
   v.push_back(20);

   for (std::vector<int>::iterator i = v.begin(); i != v.end(); ++i)
      ;   // do nothing
   --i;   // C2065
}
```

## <a name="example"></a>Örnek

Hata ayıklama yineleyiciler Önemsiz olmayan Yıkıcılar sahip. Bir yıkıcı, herhangi bir nedenle çalışmaz erişim ihlalleri ve veri bozulması meydana gelebilir. Bu örneği göz önünde bulundurun:

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

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
