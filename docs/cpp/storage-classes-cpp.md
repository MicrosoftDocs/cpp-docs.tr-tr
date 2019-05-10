---
title: Depolama sınıfları (C++)
ms.date: 11/04/2016
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 92435b2bab670dd366f26c981443e98e4a4e3c29
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221990"
---
# <a name="storage-classes-c"></a>Depolama sınıfları (C++)

A *depolama sınıfı* C++ bağlamında değişken bildirimleri olan nesnelerin ömrü, bağlantı ve bellek konumu yöneten bir tür tanımlayıcısı. Belirli bir nesne yalnızca bir depolama sınıfına sahip olabilir. Bir blok içinde tanımlanan değişkenleri kullanarak aksi belirtilmediği sürece otomatik depolama sahip **extern**, **statik**, veya `thread_local` tanımlayıcıları. Otomatik nesnelerin ve değişkenlerin hiçbir bağlantısı yoktur; Bunlar kod bloğu dışında görünür değildir.

**Notlar**

1. [Değişebilir](../cpp/mutable-data-members-cpp.md) anahtar sözcüğü bir depolama sınıfı tanımlayıcısı olarak değerlendirilebilir. Ancak, sadece bir sınıf tanımının üye listesinde kullanılabilir.

1. **Visual Studio 2010 ve sonraki sürümleri:** **Otomatik** anahtar sözcüğü, artık bir C++ depolama sınıfı tanımlayıcısı ve **kaydetme** anahtar sözcüğü kullanım dışı bırakılmıştır. **Visual Studio 2017 sürüm 15.7 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **Kaydetme** anahtar sözcüğü C++ dili kaldırılır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>Bu bölümde:

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> Statik

**Statik** anahtar sözcüğü, değişkenlerin ve işlevlerin genel kapsam, ad alanı kapsamında ve sınıf kapsamı bildirmek için kullanılabilir. Statik değişkenler yerel kapsamda bildirilmiş.

Statik süre, program başladığında ve program sona erdiğinde serbest bırakılmış bir nesne veya değişkenin ayrıldığı olduğunu anlamına gelir. Dış bağlantı, değişkenin adını değişkenin bildirildiği dosyanın dışında görünür olduğunu gösterir. Buna karşılık, iç bağlantı adı değişkenin bildirildiği dosyanın dışında görünür olmadığı anlamına gelir. Varsayılan olarak, bir nesne veya değişkenin genel ad alanında tanımlanan statik süre ve harici bağlantı vardır. **Statik** anahtar sözcüğü aşağıdaki durumlarda kullanılabilir.

1. Bir değişken veya işlev dosya kapsamında bildirdiğinizde (genel ve/veya ad alanı kapsamında), **statik** anahtar sözcüğü değişkenin veya işlevin iç bağlantısı olduğunu belirtir. Bir değişken bildirdiğinizde değişkenin süresi statiktir ve başka bir değer belirtmediğiniz sürece derleyici onu 0 olarak başlatır.

1. Bir işlev içinde bir değişken bildirdiğinizde **statik** anahtar sözcüğü değişkenin bu işleve yapılan çağrılar arasında durumunu korur belirtir.

1. Bir sınıf bildiriminde veri üyesi bildirdiğinizde **statik** anahtar sözcüğü üyenin bir kopyasının tüm sınıf örnekleri tarafından paylaşıldığını belirtir. Statik veri üyesinin dosya kapsamında tanımlanmış olması gerekir. Olarak bildirdiğiniz bir tam sayı veri üyesinin **const static** bir Başlatıcısı olabilir.

1. Bir sınıf bildiriminde üye işlevi bildirdiğinizde **statik** anahtar sözcüğü işlevin tüm sınıf örnekleri tarafından paylaşıldığını belirtir. Örtük işlev sahip olmadığı için bir statik üye işlevi bir örnek üyesi erişemiyor **bu** işaretçi. Bir örnek üyesine erişmek için işlevi bir örnek işaretçisi veya başvurusu olan bir parametreyle bildirin.

1. Statik olarak union üyelerinin bildirimini yapamazsınız. Ancak, bir genel olarak bildirilen anonim birleşim açıkça bildirilmelidir **statik**.

Bu örnek nasıl bildirilen bir değişken gösterir **statik** bir işlevde bu işleve yapılan çağrılar arasında durumunu saklar.

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

Bu örnek, kullanımını gösterir. **statik** sınıfında.

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

Bu örnek, bildirilmiş bir yerel değişkeni gösterir **statik** bir üye işlev. Statik değişken tüm program için kullanılabilir; türün tüm örnekleri statik değişkenin aynı kopyasını paylaşır.

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

C ++ 11'de başlayarak, statik bir yerel değişken başlatma iş parçacığı açısından güvenli olması sağlanır. Bu özellik adlandırılır *Sihirli statikler*. Ancak, çok iş parçacıklı bir uygulamada tüm sonraki atamalarını eşitlenmelidir. İş parçacığı güvenli statik başlatma özelliğini kullanarak devre dışı bırakılabilir [/ZC: threadsafeınit](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT'ye bağımlılık önlemek için bayrak.

## <a name="extern"></a> extern

Nesneler ve değişkenler olarak bildirilen **extern** dış bağlantıya sahip olarak sarmalayan bir kapsamda ya da başka bir çeviri biriminde tanımlanan nesne bildirme.

Deklarace **const** değişkenlerle **extern** depolama sınıfı değişkeni dış bağlantıya sahip olmasına zorlar. Bir başlatma bir **extern const** değişken tanımlayan bir çeviri birimindeki izin verilir. Çeviri birimleri tanımlama çeviri birimi dışında başlatmalarının tanımsız sonuçlar. Daha fazla bilgi için [belirtmek için extern kullanma](../cpp/using-extern-to-specify-linkage.md)

[/ZC: externconstexpr](../build/reference/zc-externconstexpr.md) derleyici seçeneği, derleyicinin uygulamak neden [dış bağlantısı](../c-language/external-linkage.md) kullanılarak bildirilen değişkenlere `extern constexpr`. Varsayılan olarak ve Visual Studio'nun önceki sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio iç bağlantı için geçerli **constexpr** değişkenleri bile **extern** anahtar sözcüğü kullanılır. **/ZC: externconstexpr** Visual Studio 2017 güncelleştirme 15.6 sürümünde başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. / ZC: externconstexpr /permissive-option etkinleştirmez.

Aşağıdaki kod iki gösterir **extern** bildirimleri, `DefinedElsewhere` (hangi başvurduğu farklı çeviri biriminde tanımlanan bir ad) ve `DefinedHere` (hangi başvurduğu bir kapsayan kapsam içinde tanımlanan bir ad):

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

Bildirilen bir değişken `thread_local` belirticisi üzerinde oluşturulduğu yalnızca iş parçacığı üzerinde erişilebilir. İş parçacığı oluşturulur ve iş parçacığı kaldırıldığında yok değişkeni oluşturulur. Her iş parçacığı, kendi değişken kopyasına sahip olur. Windows, şirket `thread_local` için Microsoft'a özgü işlevsel olarak eşdeğerdir [__declspec (iş parçacığı)](../cpp/thread.md) özniteliği.

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

- Dinamik olarak başlatılmış thread-local değişkenleri DLL'lerdeki tüm çağıran iş parçacığı üzerinde doğru şekilde başlatılmamış olabilir. Daha fazla bilgi için [iş parçacığı](thread.md).

- `thread_local` Tanımlayıcısı ile birleştirilebilir **statik** veya **extern**.

- Uygulayabileceğiniz `thread_local` sadece veri bildirimlerine ve tanımlarına; için `thread_local` İşlev bildirimlerinde veya tanımlarında kullanılamaz.

- Belirtebileceğiniz `thread_local` yalnızca statik depolama süresine sahip veri öğeleri üzerinde. Bu, genel veri nesneleri içerir (her ikisi de **statik** ve **extern**), yerel statik nesneler ve sınıfların statik veri üyeleri. Herhangi bir yerel değişken bildirildi `thread_local` başka bir depolama sınıfı sağlanır; örtük olarak statiktir blok kapsamındaki diğer bir deyişle, `thread_local` eşdeğerdir `thread_local static`.

- Belirtmelisiniz `thread_local` bildirimi ve bir iş parçacığı yerel nesnesinin tanımı için bildirim ve tanım ortaya aynı dosya veya dosyaları ayırmak.

Windows, şirket `thread_local` işlevsel olarak eşdeğerdir [gt;__declspec(thread)](../cpp/thread.md) dışında **gt;__declspec(thread)** bir tür tanımı için uygulanabilir ve C kodu geçerli değil. Mümkün olduğunda kullanın `thread_local` C++ standardının bir parçası olduğundan ve bu nedenle daha taşınabilir.

##  <a name="register"></a>  Kaydolun

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **Kaydetme** anahtar sözcüğü, artık desteklenen bir depolama sınıfı. Anahtar sözcüğü hala standart gelecekte kullanım için ayrılmıştır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Örnek: otomatik statik başlatma karşılaştırması

Denetim akışı tanımı ulaştığında her zaman yerel otomatik nesne veya değişken başlatılır. Yerel statik nesne veya değişken tanımını denetim akışını ulaştığında ilk kez başlatıldı.

Oturum Başlatma ve nesnelerin yok edilmesi ve ardından üç nesne tanımlayan bir sınıf tanımlar, aşağıdaki örneği göz önünde bulundurun `I1`, `I2`, ve `I3`:

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

Bu örnek nasıl ve ne zaman gösterir nesneleri `I1`, `I2`, ve `I3` başlatılır ve bunların ne zaman edilir.

Program hakkında dikkat edilecek bazı noktalar vardır:

- İlk olarak, `I1` ve `I2` denetim akışını blok çıktığında otomatik olarak yok, tanımlandıkları içinde.

- İkinci olarak, C++'da, nesneler veya bir blok başına değişkenleri bildirmek ise gerekli değildir. Ayrıca, denetim akışı tanımlarını ulaştığında bu nesneler başlatılır. (`I2` ve `I3` tür tanımlarını bir örnektir.) Tam olarak başlatılmış çıkış gösterir.

- Son olarak, statik yerel değişkenler gibi `I3` program süresince değerlerini korur, ancak program sona erer gibi yok edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)