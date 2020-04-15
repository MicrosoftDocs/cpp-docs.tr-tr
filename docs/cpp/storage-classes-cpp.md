---
title: Depolama sınıfları (C++)
description: C++'da statik, extern ve thread_local anahtar kelimeler, bir değişkenin veya işlevin kullanım ömrünü, bağlantısını ve bellek konumunu belirtir.
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 75ccb11689b4863d2d0df5edd6d066be6bd3858c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365356"
---
# <a name="storage-classes"></a>Depolama sınıfları

C++ değişken bildirimleri bağlamında bir *depolama sınıfı,* nesnelerin yaşam sürelerini, bağlantılarını ve bellek konumunu yöneten bir tür belirticidir. Belirli bir nesnenin yalnızca bir depolama sınıfı olabilir. Bir blok içinde tanımlanan değişkenler, **extern,** **statik**veya **thread_local** belirteçleri kullanılarak aksi belirtilmedikçe otomatik depolama alanına sahiptir. Otomatik nesnelerin ve değişkenlerin bağlantısı yoktur; bunlar blok dışında kod için görünür değildir. Yürütme bloğa girdiğinde onlar için otomatik olarak bellek ayrırılır ve blok çıktığında ayrılık devreden.

**Notlar**

1. [Mutable](../cpp/mutable-data-members-cpp.md) anahtar sözcük bir depolama sınıfı belirteç olarak kabul edilebilir. Ancak, sadece bir sınıf tanımının üye listesinde kullanılabilir.

1. **Visual Studio 2010 ve sonrası:** **Otomatik** anahtar kelime artık bir C++ depolama sınıfı belirtici değildir ve **kayıt** anahtar kelimesi amortismana kaydedilir. **Visual Studio 2017 sürüm 15.7 ve sonrası:** (/std:c++17 ile kullanılabilir ): **Kayıt** anahtar kelimesi C++ dilinden kaldırılır. [/std:c++17](../build/reference/std-specify-language-standard-version.md)

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a><a name="static"></a>Statik

**Statik** anahtar kelime, genel kapsam, ad alanı kapsamı ve sınıf kapsamı ndaki değişkenleri ve işlevleri bildirmek için kullanılabilir. Statik değişkenler yerel kapsamda da bildirilebilir.

Statik süre, program başlatıldığında nesne nin veya değişkenin ayrılacağı ve program sona erdiğinde ayrılacağı anlamına gelir. Dış bağlantı, değişkenin adının, değişkenin beyan edildiği dosyanın dışından görülebildiğinden gelir. Tersine, iç bağlantı, adın değişkenin beyan edildiği dosyanın dışında görünmediği anlamına gelir. Varsayılan olarak, genel ad alanında tanımlanan bir nesne veya değişkenin statik süresi ve dış bağlantısı vardır. **Statik** anahtar kelime aşağıdaki durumlarda kullanılabilir.

1. Dosya kapsamında (genel ve/veya ad alanı kapsamı) bir değişken veya işlev beyan ettiğinizde, **statik** anahtar kelime değişkenin veya işlevin iç bağlantıya sahip olduğunu belirtir. Bir değişkeni beyan ettiğinizde, değişkenin statik süresi vardır ve başka bir değer belirtmediğiniz sürece derleyici bunu 0 olarak aparat eder.

1. Bir işlevde bir değişkenilince, **statik** anahtar kelime değişkenin bu işleve yapılan çağrılar arasındaki durumunu koruduğunu belirtir.

1. Bir veri üyesini sınıf bildiriminde beyan ettiğinizde, **statik** anahtar kelime üyenin bir kopyasının sınıfın tüm örnekleri tarafından paylaşılıncaya dalatır. Dosya kapsamında statik bir veri üyesi tanımlanmalıdır. **Const statik** olarak beyan ettiğiniz integral bir veri üyesinin bir baş harfe sahip olabilir.

1. Bir üye işlevi sınıf bildiriminde bildirdiğinizde, **statik** anahtar kelime işlevin sınıfın tüm örnekleri tarafından paylaşılıncasını belirtir. Statik bir üye işlev, **işlevin** örtük bir bu işaretçisi olmadığından bir örnek üyeye erişemez. Bir örnek üyeye erişmek için, işlevi örnek işaretçisi veya başvuru olan bir parametreyle bildirin.

1. Bir birliğin üyelerini statik olarak beyan edemezsiniz. Ancak, genel olarak ilan edilen anonim bir birlik açıkça **statik**olarak bildirilmelidir.

Bu örnek, bir işlevde **statik** olarak bildirilen bir değişkenin, bu işleve yapılan çağrılar arasındaki durumunu nasıl koruduğunu gösterir.

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

Bu örnek, bir sınıfta **statik** kullanımını gösterir.

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

Bu örnek, bir üye işlevde **statik** olarak bildirilen yerel bir değişkeni gösterir. Statik değişken tüm program için kullanılabilir; türün tüm örnekleri statik değişkenin aynı kopyasını paylaşır.

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

C++11'den başlayarak statik yerel değişken başlatmanın iş parçacığı açısından güvenli olacağı garanti edilir. Bu özellik bazen *sihirli statik*olarak adlandırılır. Ancak, çok iş parçacığı uygulamasında sonraki tüm atamaları senkronize edilmelidir. İş parçacığı güvenli statik başlatma özelliği CRT bir bağımlılık alarak önlemek için [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) bayrağı kullanılarak devre dışı olabilir.

## <a name="extern"></a><a name="extern"></a>Extern

**Extern** olarak bildirilen nesneler ve değişkenler, başka bir çeviri biriminde veya dış bağlantıya sahip olarak tanımlanan bir nesneyi bildirir. Daha fazla bilgi için [extern](extern-cpp.md) ve [Çeviri birimleri ve bağlantı](program-and-linkage-cpp.md)bakın.

## <a name="thread_local-c11"></a><a name="thread_local"></a>thread_local (C++11)

**thread_local** belirteçli olarak bildirilen bir değişkene yalnızca oluşturulduğu iş parçacığında erişilebilir. Değişken iş parçacığı oluşturulduğunda oluşturulur ve iş parçacığı yok edildiğinde yok edilir. Her iş parçacığı değişkenin kendi kopyası vardır. Windows'da **thread_local** işlevsel olarak Microsoft'a özgü [__declspec (iş parçacığı)](../cpp/thread.md) özniteliğine eşdeğerdir.

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

**thread_local** belirtici hakkında dikkat edilmesi gerekenler:

- DL'lerde dinamik olarak başlaltımiş iş parçacığı yerel değişkenler doğru tüm arama iş parçacığı üzerinde baş harfe çevrilmeyebilir. Daha fazla bilgi için [iş parçacığına](thread.md)bakın.

- **thread_local** belirteç **statik** veya **extern**ile kombine edilebilir.

- **thread_local** yalnızca veri beyanlarına ve tanımlarına uygulayabilirsiniz; **thread_local** işlev bildirimlerinde veya tanımlarında kullanılamaz.

- yalnızca statik depolama süresine sahip veri maddelerinde **thread_local** belirtebilirsiniz. Bu, genel veri nesnelerini (hem **statik** hem de **extern),** yerel statik nesneleri ve sınıfların statik veri üyelerini içerir. **Başka depolama** sınıfı sağlanmazsa, thread_local bildirilen herhangi bir yerel değişken örtülü olarak statiktir; başka bir deyişle, **thread_local** blok kapsamı `thread_local static`thread_local eşdeğerdir.

- Bildirim ve tanım aynı dosyada veya ayrı dosyalarda bulunup bulunmadığına bakılmaksızın, hem bildirim hem de iş parçacığı yerel nesnesinin tanımı için **thread_local** belirtmeniz gerekir.

Windows'da **thread_local,** **__declspec(iş parçacığı)** bir tür tanımına uygulanabildiği ve C kodunda geçerli olması dışında işlevsel olarak [__declspec(iş parçacığı)](../cpp/thread.md) eşdeğerdir. Mümkün **olduğunda,** C++ standardının bir parçası olduğu ve bu nedenle daha taşınabilir olduğu için thread_local kullanın.

## <a name="register"></a><a name="register"></a>Kayıt yaptır

**Visual Studio 2017 sürüm 15.3 ve sonrası** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir ): **Kayıt** anahtar kelimesi artık desteklenen bir depolama sınıfı değildir. Anahtar kelime hala gelecekteki kullanım için standart ayrılmıştır.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Örnek: otomatik vs statik başlatma

Denetim akışı tanımına her ulaştığında yerel bir otomatik nesne veya değişken baş harfe doğru başharfe işlenir. Yerel statik nesne veya değişken, denetim akışı tanımına ilk ulaştığında baş harfe doğru başolarak başlar.

Nesnelerin başlatılmasını ve yok edilmesini kaydeden ve daha sonra üç nesneyi `I1` `I2`tanımlayan bir sınıfı tanımlayan `I3`aşağıdaki örneği göz önünde bulundurun:

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

Bu örnek, nesnelerin `I1` `I2`nasıl ve ne `I3` zaman ve ne zaman ortaya çıktığını ve ne zaman yok edildiğini gösterir.

Program hakkında dikkat edilmesi gereken birkaç nokta vardır:

- İlk `I1` olarak, ve `I2` otomatik olarak kontrol akışı tanımlandığı blok çıkar.

- İkinci olarak, C++'da, bir bloğun başında nesneleri veya değişkenleri bildirmek gerekli değildir. Ayrıca, bu nesneler yalnızca denetim akışı tanımlarına ulaştığında başharfe alınır. (`I2` `I3` ve bu tür tanımlara örnektir.) Çıktı tam olarak ne zaman başharflere olduğunu gösterir.

- Son olarak, program süresince değerlerini korumak gibi `I3` statik yerel değişkenler, ancak program sona erdiğinde yok edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](../cpp/declarations-and-definitions-cpp.md)
