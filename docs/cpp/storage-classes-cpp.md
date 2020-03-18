---
title: Depolama sınıfları (C++)
description: "' C++De, statik, extern ve thread_local anahtar sözcükleri bir değişkenin veya işlevin yaşam süresi, bağlantı ve bellek konumunu belirtir."
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 5b30fe7bc6665da9172f093f8ea6a2130cb900b2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447325"
---
# <a name="storage-classes"></a>Depolama sınıfları

Değişken bildirimleri bağlamındaki bir *depolama sınıfı* , nesnelerin ömür, bağlantı ve bellek konumunu yöneten bir tür belirticisidir. C++ Verilen bir nesne yalnızca bir depolama sınıfına sahip olabilir. **Dış**, **statik**veya **thread_local** belirticileri kullanılarak belirtilmediği takdirde bir blok içinde tanımlanan değişkenlerin otomatik depolaması vardır. Otomatik nesneler ve değişkenlerin bağlantısı yoktur; Bunlar, blok dışındaki kodla görülemez. Yürütme blok 'tan çıkıldığında, yürütme bloğa girdiğinde ve serbest bırakıldığında bellek otomatik olarak ayrılır.

**Notlar**

1. [Kesilebilir](../cpp/mutable-data-members-cpp.md) anahtar sözcüğü bir depolama sınıfı belirticisi olarak kabul edilebilir. Ancak, sadece bir sınıf tanımının üye listesinde kullanılabilir.

1. **Visual Studio 2010 ve üzeri:** **Auto** anahtar sözcüğü artık bir C++ depolama sınıfı belirticisi değildir ve **register** anahtar sözcüğü kullanım dışıdır. **Visual Studio 2017 sürüm 15,7 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): **register** anahtar sözcüğü C++ dilden kaldırılır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a>se

**Static** anahtar sözcüğü, genel kapsam, ad alanı kapsamı ve sınıf kapsamındaki değişkenleri ve işlevleri bildirmek için kullanılabilir. Statik değişkenler, yerel kapsamda de bildirilemez.

Statik süre, program başlatıldığında nesnenin veya değişkenin ayrıldığı ve program sona erdiğinde serbest bırakıldığı anlamına gelir. Dış bağlantı, değişkenin adının, değişkenin bildirildiği dosyanın dışından görünebileceği anlamına gelir. Buna karşılık iç bağlantı, adın, değişkenin bildirildiği dosyanın dışında görünmediği anlamına gelir. Varsayılan olarak, genel ad alanında tanımlanan bir nesne veya değişkenin statik süresi ve dış bağlantısı vardır. **Statik** anahtar sözcüğü aşağıdaki durumlarda kullanılabilir.

1. Dosya kapsamında (genel ve/veya ad alanı kapsamı) bir değişken veya işlev bildirdiğinizde, **static** anahtar sözcüğü değişkenin veya işlevin iç bağlantıya sahip olduğunu belirtir. Bir değişken bildirdiğinizde, değişken statik süreye sahiptir ve başka bir değer belirtmediğiniz takdirde derleyici bunu 0 olarak başlatır.

1. Bir işlevde bir değişken bildirdiğinizde **static** anahtar sözcüğü değişkenin bu işleve yapılan çağrılar arasında durumunu koruduğunu belirtir.

1. Bir sınıf bildiriminde bir veri üyesi bildirdiğinizde, **static** anahtar sözcüğü, üyenin bir kopyasının tüm sınıf örnekleri tarafından paylaşıldığını belirtir. Statik bir veri üyesinin dosya kapsamında tanımlanması gerekir. **Const statik** olarak bildirdiğiniz integral veri üyesi bir başlatıcıya sahip olabilir.

1. Bir sınıf bildiriminde bir üye işlevi bildirdiğinizde, **static** anahtar sözcüğü işlevin sınıfın tüm örnekleri tarafından paylaşıldığını belirtir. Bir statik üye işlevi bir örnek üyesine erişemez, çünkü işlevin örtülü **Bu** işaretçisi yok. Örnek üyesine erişmek için, işlevi örnek işaretçisi veya başvurusu olan bir parametreyle bildirin.

1. Bir birleşimin üyelerini statik olarak bildiremezsiniz. Ancak, genel olarak tanımlanmış bir anonim birleşim açıkça **statik**olarak bildirilmelidir.

Bu örnek, bir işlevde **statik** olarak tanımlanan bir değişkenin, bu işleve yapılan çağrılar arasında durumunu nasıl koruduğunu gösterir.

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

Bu örnek, bir sınıfında **statik** kullanımını gösterir.

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

Bu örnek, bir üye işlevinde **statik** olarak belirtilen yerel bir değişkeni gösterir. Statik değişken tüm program tarafından kullanılabilir; türün tüm örnekleri, statik değişkenin aynı kopyasını paylaşır.

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

C++ 11 ' den başlayarak statik bir yerel değişken başlatmanın iş parçacığı güvenli olduğu garanti edilir. Bu özellik bazen *sihirli statiği*olarak adlandırılır. Ancak, çok iş parçacıklı bir uygulamada, sonraki tüm atamaların eşitlenmesi gerekir. İş parçacığı güvenli statik başlatma özelliği, CRT üzerinde bir bağımlılık almayı önlemek için [/Zc: threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) Flag kullanılarak devre dışı bırakılabilir.

## <a name="extern"></a>Dış

**Extern** olarak belirtilen nesneler ve değişkenler, başka bir çeviri biriminde veya dış bağlantıya sahip olan bir kapsayan kapsamda tanımlanan bir nesneyi bildirir. Daha fazla bilgi için bkz. [extern](extern-cpp.md) ve [çeviri birimleri ve bağlantısı](program-and-linkage-cpp.md).

## <a name="thread_local"></a>thread_local (C++ 11)

**Thread_local** belirticisiyle belirtilen bir değişken yalnızca oluşturulduğu iş parçacığında erişilebilir. Değişkeni, iş parçacığı oluşturulduğunda oluşturulur ve iş parçacığı yok edildiğinde yok edilir. Her iş parçacığının kendi kendine ait bir kopyası vardır. Windows 'da **thread_local** , Microsoft 'a özgü [__declspec (thread)](../cpp/thread.md) özniteliğiyle işlevsel olarak eşdeğerdir.

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

**Thread_local** belirleyicisi hakkında dikkat edilmesi gerekenler:

- Dinamik olarak başlatılan iş parçacığı-dll 'Lerdeki yerel değişkenler, tüm çağıran iş parçacıklarında düzgün şekilde başlatılmamış olabilir. Daha fazla bilgi için bkz. [iş parçacığı](thread.md).

- **Thread_local** belirleyicisi **statik** veya **extern**ile birleştirilebilir.

- Yalnızca veri bildirimlerine ve tanımlarına **thread_local** uygulayabilirsiniz; **thread_local** işlev bildirimlerinde veya tanımlarında kullanılamaz.

- Yalnızca statik depolama süresine sahip veri öğelerinde **thread_local** belirtebilirsiniz. Buna genel veri nesneleri ( **statik** ve **extern**), yerel statik nesneler ve sınıfların statik veri üyeleri dahildir. Başka bir depolama sınıfı sağlanmazsa **thread_local** tarafından belirtilen herhangi bir yerel değişken örtük olarak statiktir; diğer bir deyişle, blok kapsamında **thread_local** `thread_local static`eşdeğerdir.

- Bildirim ve tanımın aynı dosyada veya ayrı dosyalarda oluşmasına bakılmaksızın hem bildirim hem de iş parçacığı yerel nesnesinin tanımı için **thread_local** belirtmeniz gerekir.

Windows 'da, bir tür tanımına **__declspec (iş parçacığı)** uygulanamadığından ve C kodunda geçerliyse, **thread_local** işlevsel olarak [__declspec (iş parçacığı)](../cpp/thread.md) ile eşdeğerdir. Mümkün olduğunda, C++ standart bir parçası olduğundan ve bu nedenle daha taşınabilir olduğundan **thread_local** kullanın.

##  <a name="register"></a>kaydolunamadı

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): **register** anahtar sözcüğü artık desteklenen bir depolama sınıfı değil. Anahtar sözcüğü, daha sonra kullanılmak üzere hala standart olarak ayrılmıştır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Örnek: otomatik ve statik başlatma

Her denetim akışı tanımına ulaştığında yerel bir otomatik nesne veya değişken başlatılır. Bir yerel statik nesne veya değişken, denetimin akışı tanımına ulaştığında ilk kez başlatılır.

Nesneleri başlatma ve yok etme ve sonra üç nesne (`I1`, `I2`ve `I3`tanımlayan bir sınıfı tanımlayan aşağıdaki örneği göz önünde bulundurun:

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

Bu örnek, nesneleri `I1`, `I2`ve `I3` nasıl ve ne zaman yok edildiğini gösterir.

Program hakkında daha fazla noktaya göz önünde bulunur:

- İlk, `I1` ve `I2`, denetimin akışı tanımlandıkları bloğundan çıktığında otomatik olarak yok edilir.

- İkincisi, içinde C++, bir bloğun başlangıcında nesneleri veya değişkenleri bildirmek gerekli değildir. Ayrıca, bu nesneler yalnızca denetimin akışı tanımlarına ulaştığında başlatılır. (`I2` ve `I3`, bu tür tanımlara örnektir.) Çıktı, başlatıldıklarında tam olarak gösterilir.

- Son olarak, `I3` gibi statik yerel değişkenler, programın süresi boyunca değerlerini korurlar, ancak program sonlandırıldığında yok edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)