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
ms.openlocfilehash: 9042093bb073807e9bb1476ab514c82010aeab70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394070"
---
# <a name="debug-iterator-support"></a>Hata Ayıklama Yineleyicisi Desteği

Visual C++ çalışma zamanı kitaplığı, yanlış yineleyici kullanımını algılar ve onaylar ve çalışma zamanında bir iletişim kutusu görüntüler. Hata ayıklama yineleyici desteği etkinleştirmek için programınızı derlemek için C çalışma zamanı kitaplığı ve standart C++ Kitaplığı hata ayıklama sürümleri kullanmanız gerekir. Daha fazla bilgi için [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md). İşaretli yineleyiciler kullanma hakkında daha fazla bilgi için bkz: [Checked Iterators](../standard-library/checked-iterators.md).

Standart C++ üye işlevleri geçersiz olmasına Yineleyicilerin bir kapsayıcıya nasıl neden olabilecek açıklar. İki örnek verilmiştir:

- Bir kapsayıcı bir öğeyi silme yineleyicileriyle öğesi geçersiz olmasına neden olur.

- Artırıldığında bir [vektör](../standard-library/vector.md) kullanarak anında iletme veya nedenler yineleyiciler içine Ekle `vector` geçersiz olacak.

## <a name="invalid-iterators"></a>Geçersiz yineleyiciler

Bu örnek program hata ayıklama modunda derlemek, çalışma zamanında onaylar ve sonlandırır.

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

## <a name="using-iteratordebuglevel"></a>_Iterator_debug_level kullanma

Önişlemci makrosu kullanabileceğiniz [_ıterator_debug_level](../standard-library/iterator-debug-level.md) özellik hata ayıklama derlemesinde hata ayıklama yineleyici devre dışı bırakmak için. Bu program assert değil, ancak yine de tanımsız davranış tetikler.

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

## <a name="unitialized-iterators"></a>Unitialized yineleyiciler

Assert da başlatılmadan önce aşağıda gösterildiği gibi bir yineleyici kullanmayı denerseniz oluşur:

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

Aşağıdaki kod örneği bir onaylama işlemi olduğundan neden için iki yineleyici [for_each](../standard-library/algorithm-functions.md#for_each) algoritması uyumsuz. Aynı kapsayıcı için sağlanan yineleyiciler anılıp anılmadığını algoritmaları denetleyin.

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

Bu örnek, lambda ifadesi kullanır bildirimi `[] (int& elem) { elem *= 2; }` bir functor yerine. Bu seçenek onay hatası ilgisi yoktur ancak — benzer bir işlev ise aynı hataya neden — lambdalar compact işlev nesnesi görevleri gerçekleştirmek için çok kullanışlı bir yol olan. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="iterators-going-out-of-scope"></a>Kapsam dışına giderek yineleyiciler

Hata ayıklama yineleyici denetimleri de içinde bildirilen bir yineleyici değişken neden bir **için** tanesi olmasını döngü ne zaman kapsam **için** kapsamı sona erene döngü.

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

Hata ayıklama yineleyiciler Önemsiz yok ediciler sahip. Bir yok edici çalışmaz, ancak nesnenin belleği serbest erişim ihlalleri ve veri bozulması meydana gelebilir. Bu örneği göz önünde bulundurun:

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
