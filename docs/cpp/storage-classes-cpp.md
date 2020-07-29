---
title: Depolama sınıfları (C++)
description: C++ ' da, statik, extern ve thread_local anahtar sözcükleri bir değişkenin veya işlevin yaşam süresi, bağlantı ve bellek konumunu belirtir.
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: c3fc87980d1fd0af5b803a8e590855f6429c847e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213170"
---
# <a name="storage-classes"></a>Depolama sınıfları

C++ değişken bildirimleri bağlamındaki bir *depolama sınıfı* , nesnelerin ömür, bağlantı ve bellek konumunu yöneten bir tür belirticisidir. Verilen bir nesne yalnızca bir depolama sınıfına sahip olabilir. ,, Veya belirticileri kullanılarak belirtilmediği takdirde bir blok içinde tanımlanan değişkenler otomatik depolamaya sahiptir **`extern`** **`static`** **`thread_local`** . Otomatik nesneler ve değişkenlerin bağlantısı yoktur; Bunlar, blok dışındaki kodla görülemez. Yürütme blok 'tan çıkıldığında, yürütme bloğa girdiğinde ve serbest bırakıldığında bellek otomatik olarak ayrılır.

**Notlar**

1. [Kesilebilir](../cpp/mutable-data-members-cpp.md) anahtar sözcüğü bir depolama sınıfı belirticisi olarak kabul edilebilir. Ancak, sadece bir sınıf tanımının üye listesinde kullanılabilir.

1. **Visual Studio 2010 ve üzeri:** **`auto`** Anahtar sözcüğü artık C++ depolama sınıfı Belirleyicisi değildir ve **`register`** anahtar sözcüğü kullanım dışıdır. **Visual Studio 2017 sürüm 15,7 ve üzeri:** (ile kullanılabilir [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** anahtar sözcüğü C++ dilinden kaldırılır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a><a name="static"></a> `static`

**`static`** Anahtar sözcüğü, genel kapsam, ad alanı kapsamı ve sınıf kapsamındaki değişkenleri ve işlevleri bildirmek için kullanılabilir. Statik değişkenler, yerel kapsamda de bildirilemez.

Statik süre, program başlatıldığında nesnenin veya değişkenin ayrıldığı ve program sona erdiğinde serbest bırakıldığı anlamına gelir. Dış bağlantı, değişkenin adının, değişkenin bildirildiği dosyanın dışından görünebileceği anlamına gelir. Buna karşılık iç bağlantı, adın, değişkenin bildirildiği dosyanın dışında görünmediği anlamına gelir. Varsayılan olarak, genel ad alanında tanımlanan bir nesne veya değişkenin statik süresi ve dış bağlantısı vardır. **`static`** Anahtar sözcüğü aşağıdaki durumlarda kullanılabilir.

1. Dosya kapsamında (genel ve/veya ad alanı kapsamı) bir değişken veya işlev bildirdiğinizde, **`static`** anahtar sözcüğü değişkenin veya işlevin iç bağlantı olduğunu belirtir. Bir değişken bildirdiğinizde, değişken statik süreye sahiptir ve başka bir değer belirtmediğiniz takdirde derleyici bunu 0 olarak başlatır.

1. Bir işlevde bir değişken bildirdiğinizde, **`static`** anahtar sözcüğü değişkenin bu işleve yapılan çağrılar arasında durumunu koruduğunu belirtir.

1. Bir sınıf bildiriminde bir veri üyesi bildirdiğinizde **`static`** anahtar sözcüğü, üyenin bir kopyasının tüm sınıf örnekleri tarafından paylaşıldığını belirtir. Statik bir veri üyesinin dosya kapsamında tanımlanması gerekir. Olarak bildirdiğiniz bir integral veri üyesinin **`const static`** bir başlatıcısı olabilir.

1. Bir sınıf bildiriminde bir üye işlevi bildirdiğinizde, **`static`** anahtar sözcüğü işlevin sınıfın tüm örnekleri tarafından paylaşıldığını belirtir. İşlevin örtük bir işaretçisi olmadığından, statik üye işlevi bir örnek üyesine erişemez **`this`** . Örnek üyesine erişmek için, işlevi örnek işaretçisi veya başvurusu olan bir parametreyle bildirin.

1. Bir birleşimin üyelerini statik olarak bildiremezsiniz. Ancak, genel olarak tanımlanmış bir anonim birleşim açıkça bildirilmelidir **`static`** .

Bu örnek **`static`** , bir işlevde belirtilen değişkenin, bu işleve yapılan çağrılar arasında durumunu nasıl koruduğunu gösterir.

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

Bu örnek, bir sınıfında öğesinin kullanımını gösterir **`static`** .

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

Bu örnek **`static`** , bir üye işlevinde belirtilen yerel bir değişkeni gösterir. **`static`** Değişken tüm program tarafından kullanılabilir; türün tüm örnekleri değişkenin aynı kopyasını paylaşır **`static`** .

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

C++ 11 ' den başlayarak, **`static`** yerel bir değişken başlatmanın iş parçacığı güvenli olduğu garanti edilir. Bu özellik bazen *sihirli statiği*olarak adlandırılır. Ancak, çok iş parçacıklı bir uygulamada, sonraki tüm atamaların eşitlenmesi gerekir. İş parçacığı güvenli statik başlatma özelliği, [`/Zc:threadSafeInit-`](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT üzerinde bir bağımlılık almayı önlemek için bayrağını kullanarak devre dışı bırakılabilir.

## <a name="extern"></a><a name="extern"></a> `extern`

**`extern`** Başka bir çeviri biriminde veya dış bağlantı içeren bir kapsayan kapsamda tanımlanan bir nesneyi bildirmek olarak belirtilen nesneler ve değişkenler. Daha fazla bilgi için bkz [`extern`](extern-cpp.md) . ve [çeviri birimleri ve bağlantısı](program-and-linkage-cpp.md).

## <a name="thread_local-c11"></a><a name="thread_local"></a>`thread_local`(C++ 11)

Belirticiyle belirtilen bir değişken **`thread_local`** yalnızca oluşturulduğu iş parçacığında erişilebilir. Değişkeni, iş parçacığı oluşturulduğunda oluşturulur ve iş parçacığı yok edildiğinde yok edilir. Her iş parçacığının kendi kendine ait bir kopyası vardır. Windows 'da, **`thread_local`** Microsoft 'a özgü özniteliğe işlevsel olarak eşdeğerdir [`__declspec( thread )`](../cpp/thread.md) .

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

Belirleyici ilgili dikkat edilmesi gerekenler **`thread_local`** :

- Dinamik olarak başlatılan iş parçacığı-dll 'Lerdeki yerel değişkenler, tüm çağıran iş parçacıklarında düzgün şekilde başlatılmamış olabilir. Daha fazla bilgi için bkz. [`thread`](thread.md).

- **`thread_local`** Belirleyici veya ile birleştirilebilir **`static`** **`extern`** .

- **`thread_local`** Yalnızca veri bildirimleri ve tanımlarına uygulayabilirsiniz; **`thread_local`** işlev bildirimlerinde veya tanımlarında kullanılamaz.

- **`thread_local`** Yalnızca statik depolama süresine sahip veri öğelerinde belirtebilirsiniz. Buna genel veri nesneleri (hem hem **`static`** de **`extern`** ), yerel statik nesneler ve sınıfların statik veri üyeleri dahildir. Başka bir depolama sınıfı sağlanmazsa, belirtilen herhangi bir yerel değişken **`thread_local`** örtük olarak statiktir; diğer bir deyişle, blok kapsamındaki kapsam **`thread_local`** değerine eşdeğerdir **`thread_local static`** .

- **`thread_local`** Bildirim ve tanımın aynı dosyada veya ayrı dosyalarda oluşmasına bakılmaksızın hem bildirim hem de iş parçacığı yerel nesnesinin tanımı için belirtmeniz gerekir.

Windows üzerinde, **`thread_local`** [`__declspec(thread)`](../cpp/thread.md) *`*__declspec(thread)`* * bir tür tanımına uygulanamadığından ve C kodunda geçerliyse, işlevsel olarak eşdeğerdir. Mümkün olan her durumda, **`thread_local`** C++ standardının bir parçası olduğundan ve bu nedenle daha taşınabilir olduğundan kullanın.

## <a name="register"></a><a name="register"></a>kaydolunamadı

**Visual Studio 2017 sürüm 15,3 ve üzeri** (ile kullanılabilir [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** anahtar sözcük artık desteklenen bir depolama sınıfı değil. Anahtar sözcüğü, daha sonra kullanılmak üzere hala standart olarak ayrılmıştır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Örnek: otomatik ve statik başlatma

Her denetim akışı tanımına ulaştığında yerel bir otomatik nesne veya değişken başlatılır. Bir yerel statik nesne veya değişken, denetimin akışı tanımına ulaştığında ilk kez başlatılır.

Başlatma ve nesneleri yok etme ve ardından üç nesne,,, ve tanımlayan bir sınıfı tanımlayan aşağıdaki örneği göz önünde bulundurun `I1` `I2` `I3` :

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

Bu örnek, ve nesnelerinin nasıl ve ne `I1` zaman `I2` `I3` başlatıldığını ve ne zaman yok edildiğini gösterir.

Program hakkında daha fazla noktaya göz önünde bulunur:

- İlk olarak `I1` , `I2` Denetim akışı tanımlandıkları bloğundan çıktığında otomatik olarak yok edilir.

- İkincisi, C++ ' da, bir bloğun başlangıcında nesneleri veya değişkenleri bildirmek gerekli değildir. Ayrıca, bu nesneler yalnızca denetimin akışı tanımlarına ulaştığında başlatılır. ( `I2` ve `I3` Bu tür tanımlara örnektir.) Çıktı, başlatıldıklarında tam olarak gösterilir.

- Son olarak, statik yerel değişkenler `I3` Programın süresi boyunca değerlerini korurlar, ancak program sonlandırıldığında yok edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve tanımlar](../cpp/declarations-and-definitions-cpp.md)
