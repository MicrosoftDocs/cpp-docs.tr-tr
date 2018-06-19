---
title: Depolama sınıfları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
dev_langs:
- C++
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a56d456564dc171292e8a58b6cb486ce2dfbaf31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32424595"
---
# <a name="storage-classes-c"></a>Depolama sınıfları (C++)  
  
A *depolama sınıfı* C++ bağlamında değişken bildirimleri olduğu nesnelerin ömrü, bağlantı ve bellek konumu yöneten bir tür belirteci. Belirli bir nesne yalnızca bir depolama sınıfı olabilir. Bir blok içinde tanımlanan değişkenler kullanarak aksi belirtilmediği sürece otomatik depolama sahip `extern`, `static`, veya `thread_local` tanımlayıcıları. Otomatik nesneleri ve değişkenleri bağlantısı vardır; Bunlar, kod bloğunun dışında görünür değildir.  
  
**Notlar**  
  
1.  [Değişebilir](../cpp/mutable-data-members-cpp.md) anahtar sözcük depolama sınıfı tanımlayıcısı kabul. Ancak, sadece bir sınıf tanımının üye listesinde kullanılabilir.  
  
2.  **Visual C++ 2010 ve sonraki sürümleri:** `auto` sözcüktür artık C++ depolama sınıfı tanımlayıcısı ve `register` anahtar sözcüğü kullanım dışıdır. **Visual Studio 2017 15.7 ve sonraki sürümleri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): `register` anahtar sözcüğü C++ dili kaldırılır.


```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>Bu bölümde:

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> Statik

`static` Anahtar sözcüğü, değişkenler ve genel kapsam, ad alanı kapsamı ve sınıf kapsamı işlevleri bildirmek için kullanılabilir. Statik değişkenler ayrıca yerel kapsamda bildirilebilir.

Statik süresi program başlar ve program sona erdiğinde deallocated nesne veya değişken ayrılan olduğunu anlamına gelir. Dış bağlantı değişkeninin adı değişkeni olarak bildirilen dosyası dışında görünür olduğunu gösterir. Buna karşılık, iç bağlantı adı değişkeni olarak bildirilen dosyası dışında görünür olmadığı anlamına gelir. Varsayılan olarak, bir nesneye veya genel ad alanında tanımlı değişkeni statik süresi ve dış bağlantı vardır. `static` Anahtar sözcüğünü aşağıdaki durumlarda kullanılabilir.

1. Ne zaman bildirdiğiniz değişken ya da dosya kapsamında işlevi (genel ve/veya ad alanı kapsam), `static` anahtar sözcüğü, değişken veya işlev iç bağlantı olduğunu belirtir. Bir değişken bildirirken değişkeni statik süresi olan ve başka bir değer belirtmediğiniz sürece derleyici da 0 olarak başlatır.

1. Bir işlevdeki bir değişken bildirirken `static` anahtar sözcüğü belirtir değişkeni durumuna bu işlev çağrıları arasında korur.

1. Sınıf bildirimindeki veri üyesi bildirirken `static` anahtar sözcüğü belirtir üye bir kopyasını sınıfın tüm örnekleri tarafından paylaşılır. Statik veri üyesi dosya kapsamda tanımlanması gerekir. Olarak bildirin bir tam sayı veri üyesi `const static` bir başlatıcı olabilir.

1. Sınıf bildirimindeki üye işlevi bildirirken `static` anahtar sözcüğü belirtir işlevi sınıfın tüm örnekleri tarafından paylaşılır. Statik üye işlevi işlevi örtülü olmadığından örnek üyesine erişemiyor `this` işaretçi. Örnek üyesine erişmek için bir örnek işaretçi veya başvurusu olan bir parametreyi işleviyle bildirin.

1. Statik olarak bir birleşim üyeleri bildiremezsiniz. Ancak, genel olarak bildirilen anonim UNION açıkça bildirilmelidir `static`.

Bu örnek, bir değişkeni nasıl bildirilen gösterir `static` durumuna bu işlev çağrıları arasındaki bir işlevde korur.

```cpp
// static1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void showstat( int curr ) {
   static int nStatic;    // Value of nStatic is retained
                          // between each function call
   nStatic += curr;
   cout << "nStatic is " << nStatic << endl;
}

int main() {
   for ( int i = 0; i < 5; i++ )
      showstat( i );
}
```

```Output
nStatic is 0
nStatic is 1
nStatic is 3
nStatic is 6
nStatic is 10
```

Bu örnek kullanımı gösterilmiştir `static` bir sınıf.

```cpp
// static2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CMyClass {
public:
   static int m_i;
};

int CMyClass::m_i = 0;
CMyClass myObject1;
CMyClass myObject2;

int main() {
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject1.m_i = 1;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject2.m_i = 2;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   CMyClass::m_i = 3;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;
}
```

```Output
0
0
1
1
2
2
3
3
```

Bu örnek, bildirilen yerel değişken gösterir `static` bir üye işlev. Statik değişken bütün program kullanılabilir; türünün tüm örneklerini statik değişken aynı kopyasını paylaşır.

```cpp
// static3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
struct C {
   void Test(int value) {
      static int var = 0;
      if (var == value) 
         cout << "var == value" << endl;
      else
         cout << "var != value" << endl;

      var = value;
   }
}; 

int main() {
   C c1;
   C c2;
   c1.Test(100);
   c2.Test(100);
}
```

```Output
var != value
var == value
```

C ++ 11 başlayarak, bir statik yerel değişken başlatma iş parçacığı açısından güvenli olması sağlanır. Bu özellik bazen adlı *Sihirli istatistikleri*. Ancak, birden çok iş parçacıklı uygulamada tüm sonraki atamaları eşitlenmelidir. İş parçacığı statik başlatma özelliğini kullanarak devre dışı bırakılabilir [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) bayrağı CRT üzerinde bir bağımlılık almaktan kaçının.

## <a name="extern"></a> extern

Nesneleri ve olarak bildirilen değişkenlerin `extern` başka bir çeviri birimindeki veya dış bağlantı olarak kapsayan bir kapsam içinde tanımlanan bir nesne bildirme.

Bildirimi `const` değişkenlerle `extern` depolama sınıfı dış bağlantı sağlamak için değişken zorlar. Bir başlatma bir `extern const` değişkeni tanımlama çeviri biriminde izin verilir. Çeviri birimleri tanımlama çeviri birim dışında başlatmaları tanımsız sonuçlar. Daha fazla bilgi için bkz: [bağlantıyı belirtmek için extern kullanma](../cpp/using-extern-to-specify-linkage.md)

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği neden uygulamak derleyici [dış bağlantı]() kullanarak bildirilen değişkenlerin için **extern constexpr**. Visual Studio ve varsayılan olarak eski sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio geçerlidir iç bağlantı **constexpr** olsa bile değişkenleri **extern** anahtar sözcüğü kullanılır. **/Zc:externConstexpr** Visual Studio 2017 güncelleştirme 15,6 başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. /Permissive-option /Zc:externConstexpr etkinleştirmez.

Aşağıdaki kod iki gösterir `extern` bildirimleri, `DefinedElsewhere` (hangi başvurduğu farklı çeviri biriminde tanımlanan bir ad) ve `DefinedHere` (hangi başvurduğu kapsayan bir kapsamda tanımlanan bir ad):

```cpp
// external.cpp
// DefinedElsewhere is defined in another translation unit
extern int DefinedElsewhere;   
int main() {
   int DefinedHere; 
   {
      // refers to DefinedHere in the enclosing scope
      extern int DefinedHere;
   }
}
```

## <a name="thread_local"></a> thread_local (C ++ 11)

İle bildirilen bir değişken `thread_local` belirticisi üzerinde onu oluşturulduğu yalnızca iş parçacığı üzerinde erişilebilir. İş parçacığı oluşturduğunuzda ve iş parçacığı bozulduğunda yok değişkeni oluşturulur. Her iş parçacığı değişkeni kopyasını vardır. Windows, `thread_local` için Microsoft'a özgü işlevsel olarak eşdeğerdir [__declspec (iş parçacığı)](../cpp/thread.md) özniteliği.

```cpp
thread_local float f = 42.0; // Global namespace. Not implicitly static.

struct S // cannot be applied to type definition
{
    thread_local int i; // Illegal. The member must be static.
    thread_local static char buf[10]; // OK 
};

void DoSomething()
{
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;
}
```

Hakkında dikkat edilecek noktalar `thread_local` tanımlayıcısı:

- DLL'leri dinamik olarak başlatılan iş parçacığı yerel değişkenleri tüm çağıran iş parçacığı üzerinde düzgün başlatılmamış olabilir. Daha fazla bilgi için bkz: [iş parçacığı](thread.md).

-  `thread_local` Tanımlayıcısı ile birleştirilebilir `static` veya `extern`.

-  Uygulayabileceğiniz `thread_local` yalnızca veri bildirimler ve tanımlar; için `thread_local` işlevi bildirimlerinde veya tanımlarında kullanılamaz.

-  Belirleyebileceğiniz `thread_local` yalnızca üzerinde veri öğeleri statik depolama süresi ile. Bu genel veri nesnelerini içerir (her ikisi de `static` ve `extern`), yerel statik nesneler ve sınıflar statik veri üyeleri. Herhangi bir yerel değişken bildirilen `thread_local` başka bir depolama sınıf sağladıysanız; örtük olarak statik diğer bir deyişle, blok kapsamında `thread_local` eşdeğerdir `thread_local static`. 

-  Belirtmeniz gerekir `thread_local` bildirimi ve bir iş parçacığı yerel nesnesinin tanımı için bildirim ve tanımı ortaya olup olmadığını aynı dosya veya ayrı dosyalar.

Windows, `thread_local` işlevsel olarak eşdeğerdir [__declspec(thread)](../cpp/thread.md) dışında `__declspec(thread)` bir tür tanımı için uygulanabilir ve C kodu geçerli değil. Mümkün olduğunda kullanın `thread_local` C++ standart bir parçası olduğundan ve bu nedenle daha taşınabilir.

##  <a name="register"></a>  Kaydetme

**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): `register` sözcüktür artık desteklenen depolama sınıfı. Anahtar sözcüğü standart gelecekte kullanım için ayrılmış olarak kalır. 

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Örnek: otomatik statik başlatma karşılaştırması

Denetim akışı tanımına eriştiği her zaman bir yerel otomatik nesnesi veya değişken başlatılır. Bir yerel statik nesne veya değişken tanımını denetim akışını ulaştığında ilk kez başlatıldı.

Başlatma ve nesneleri yok etme kaydeder ve üç nesneleri tanımlayan bir sınıf tanımlar, aşağıdaki örnekte, göz önünde bulundurun `I1`, `I2`, ve `I3`:

```cpp
// initialization_of_objects.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>
using namespace std;

// Define a class that logs initializations and destructions.
class InitDemo {
public:
    InitDemo( const char *szWhat );
    ~InitDemo();

private:
    char *szObjName;
    size_t sizeofObjName;
};

// Constructor for class InitDemo
InitDemo::InitDemo( const char *szWhat ) :
    szObjName(NULL), sizeofObjName(0) {
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {
        // Allocate storage for szObjName, then copy
        // initializer szWhat into szObjName, using
        // secured CRT functions.
        sizeofObjName = strlen( szWhat ) + 1;

        szObjName = new char[ sizeofObjName ];
        strcpy_s( szObjName, sizeofObjName, szWhat );

        cout << "Initializing: " << szObjName << "\n";
    }
    else {
        szObjName = 0;
    }
}

// Destructor for InitDemo
InitDemo::~InitDemo() {
    if( szObjName != 0 ) {
        cout << "Destroying: " << szObjName << "\n";
        delete szObjName;
    }
}

// Enter main function
int main() {
    InitDemo I1( "Auto I1" ); {
        cout << "In block.\n";
        InitDemo I2( "Auto I2" );
        static InitDemo I3( "Static I3" );
    }
    cout << "Exited block.\n";
}
```

```Output
Initializing: Auto I1
In block.
Initializing: Auto I2
Initializing: Static I3
Destroying: Auto I2
Exited block.
Destroying: Auto I1
Destroying: Static I3
```

Bu örnek nasıl ve ne zaman gösterir nesneleri `I1`, `I2`, ve `I3` başlatılır ve bunların ne zaman kaybolur.

Program hakkında dikkat edilecek birkaç nokta vardır:

- İlk olarak, `I1` ve `I2` denetim akışı blok çıktığında otomatik olarak yok içinde bunlar tanımlanır.

- İkinci olarak, C++'da, nesneler veya değişkenleri bir bloğun başlangıcında bildirmek ise gerekli değildir. Ayrıca, bu nesneler yalnızca denetim akışını tanımlarını ulaştığında başlatılır. (`I2` ve `I3` tür tanımları örnekleridir.) Tam olarak başlatılmadı çıkış gösterir.

- Son olarak, statik yerel değişkenler gibi `I3` program süresince değerlerini korur, ancak programın sonlandırır olarak yok.

## <a name="see-also"></a>Ayrıca Bkz.

 [Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)
