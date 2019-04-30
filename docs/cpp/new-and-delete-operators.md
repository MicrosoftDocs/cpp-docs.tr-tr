---
title: new ve delete İşleçleri
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 1ac6282ecbf45f22e7dd66b94f8bccdbc4e505ce
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345891"
---
# <a name="new-and-delete-operators"></a>new ve delete İşleçleri

C++ dinamik ayırmayı ve ayırmayı kaldırma kullanarak nesneleri destekler [yeni](../cpp/new-operator-cpp.md) ve [Sil](../cpp/delete-operator-cpp.md) işleçleri. Bu işleçler, kullanılabilir depolama alanı olarak adlandırılan bir havuzdan nesneler için bellek ayrılamadı. **Yeni** işlecini çağıran özel işlev [new işleci](../cpp/new-operator-cpp.md)ve **Sil** işlecini çağıran özel işlev [delete işleci](../cpp/delete-operator-cpp.md).

**Yeni** işlevi C++ standart kitaplık içinde belirtilen davranışı destekler C++ bellek ayırma başarısız olursa bir std::bad_alloc özel durum için olan standart. Hala oluşturmayan sürümü istiyorsanız **yeni**, programınızı nothrownew.obj ile bağlayın. Bununla birlikte, varsayılan nothrownew.obj ile bağladığınızda **new işleci** C++ Standart Kitaplığı'nda artık çalışmaz.

C çalışma zamanı kitaplığı ve C++ Standart Kitaplığı oluşturan kitaplığı dosyaların bir listesi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

##  <a id="new_operator"> </a> New işleci

Bir programda aşağıdaki gibi bir deyimle karşılaşıldığında, işlevine bir çağrı çevirir **new işleci**:

```cpp
char *pch = new char[BUFFER_SIZE];
```

İstek için depolama alanı, sıfır bayt ise **new işleci** farklı nesneye bir işaretçi döndürür (diğer bir deyişle, çağrı yinelenen **new işleci** farklı işaretçiler döndürür). Yetersiz bellek ayırma isteği için ise **new işleci** std::bad_alloc özel durumu oluşturur veya döndürür **nullptr** oluşturmayan içinde bağladıysanız **new işleci** destekler.

Belleği boşaltmak ve ayırma yeniden başlatmayı deneyen bir yordam yazabilirsiniz; bkz: [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) daha fazla bilgi için. Kurtarma düzeni hakkında daha fazla ayrıntı için bu konunun işleme yetersiz bellek bölümüne bakın.

Yönelik iki kapsam **new işleci** işlevleri, aşağıdaki tabloda açıklanmıştır.

### <a name="scope-for-operator-new-functions"></a>new işleci işlevlerine yönelik kapsam

|İşleç|Kapsam|
|--------------|-----------|
|**:: new işleci**|Global|
|*sınıf adı* **:: new işleci**|örneği|

İlk bağımsız değişkeni **new işleci** türünde olmalıdır `size_t` (tanımlanan bir türü \<stddef.h >), ve dönüş türü her zaman **void** <strong>\*</strong>.

Genel **new işleci** işlevi çağrılır **yeni** işleci yerleşik türlerin nesnelerini, ayırmak için kullanıldığında, içermeyen sınıf türünün nesnelerini kullanıcı tarafından tanımlanan **new işleci** işlevleri ve herhangi bir türde diziler. Zaman **yeni** işleci, sınıf türünden nesneleri ayırmak için kullanılır burada bir **new işleci** tanımlanmışsa, bu sınıfın **new işleci** çağrılır.

Bir **new işleci** küreseli gizliyor (Bu nedenle sanal olamaz) bir statik üye işlevi bir sınıf için tanımlanan işlev **new işleci** o sınıf türü nesneler için işlevi. Bir durum düşünün burada **yeni** ayırma ve bellek belirli bir değere ayarlamak için kullanılır:

```cpp
// spec1_the_operator_new_function1.cpp
#include <malloc.h>
#include <memory.h>

class Blanks
{
public:
    Blanks(){}
    void *operator new( size_t stAllocateBlock, char chInit );
};
void *Blanks::operator new( size_t stAllocateBlock, char chInit )
{
    void *pvTemp = malloc( stAllocateBlock );
    if( pvTemp != 0 )
        memset( pvTemp, chInit, stAllocateBlock );
    return pvTemp;
}
// For discrete objects of type Blanks, the global operator new function
// is hidden. Therefore, the following code allocates an object of type
// Blanks and initializes it to 0xa5
int main()
{
   Blanks *a5 = new(0xa5) Blanks;
   return a5 != 0;
}
```

Parantez içinde sağlanan bağımsız değişken **yeni** geçirilir `Blanks::operator new` olarak `chInit` bağımsız değişken. Ancak, genel **new işleci** işlev gizlendi, bir hata oluşturmak için aşağıdaki gibi kod neden:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Visual C++ 5.0 ve önceki sürümlerde olmayan türler ve tüm diziler (olup olmadıklarına bakılmaksızın **sınıfı** türü) kullanılarak ayrılmış **yeni** işleci her zaman kullanılan genel **new işleci** işlevi.

Visual C++ 5.0 ile başlayan, derleyici üye dizisi destekler **yeni** ve **Sil** bir sınıf bildiriminde işleçleri. Örneğin:

```cpp
// spec1_the_operator_new_function2.cpp
class MyClass
{
public:
   void * operator new[] (size_t)
   {
      return 0;
   }
   void   operator delete[] (void*)
   {
   }
};

int main()
{
   MyClass *pMyClass = new MyClass[5];
   delete [] pMyClass;
}
```

### <a name="handling-insufficient-memory"></a>Yetersiz bellek işleme

Başarısız bellek ayırmaya yönelik test, aşağıdaki gibi kod ile yapılabilir:

```cpp
// insufficient_memory_conditions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
#define BIG_NUMBER 100000000
int main() {
   int *pI = new int[BIG_NUMBER];
   if( pI == 0x0 ) {
      cout << "Insufficient memory" << endl;
      return -1;
   }
}
```

Başarısız bellek ayırma isteklerini işlemek için başka yollar vardır: Böyle bir hatayı işlemek için bir özel kurtarma yordamı yazın, ardından çağırarak işlevinizi kaydedin [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı işlevi.

##  <a id="delete_operator"> </a> Delete işleci

Kullanarak dinamik olarak atanan bellek **yeni** işleci kullanılarak serbest bırakılan **Sil** işleci. Delete işleci çağrıları **delete işleci** işlevin bellek kullanılabilir havuzuna serbest bırakır. Kullanarak **Sil** işleci ayrıca neden olan sınıf yok edicisini (varsa) çağrılabilir.

Genel ve sınıf kapsamı vardır **delete işleci** işlevleri. Yalnızca bir **delete işleci** işlevi için belirli bir sınıfın tanımlanabilir; tanımlanmışsa küreseli gizliyor **delete işleci** işlevi. Genel **delete işleci** işlevi her zaman herhangi bir türde diziler için çağrılır.

Genel **delete işleci** işlevi. İki tür genel için mevcut **delete işleci** ve sınıf üyesi **delete işleci** İşlevler:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Önceki iki formu yalnızca biri için belirli bir sınıfın bulunabilir. İlk türünde tek bir bağımsız değişken alır `void *`, serbest bırakmak nesneye bir işaretçi içerir. İkinci form — boyutlandırılmış ayırmayı kaldırma — İlki bir bellek bloğunu serbest işaretçisidir ve ikinci serbest bırakmak bayt sayısıdır. iki bağımsız değişkeni alır. Her iki biçimi dönüş türü **void** (**delete işleci** bir dönüş değeri olamaz).

İkinci form amacı genellikle ayırma depolanan ve büyük olasılıkla önbelleğe alınmamış Silinecek nesnenin doğru boyutta kategori için arama ayarlama için hızıdır; İkinci form olduğunda özellikle yararlı bir **delete işleci** işlevi bir temel sınıftan türetilmiş bir sınıfın bir nesnesini silmek için kullanılır.

**Delete işleci** işlevi statik; bu nedenle sanal olamaz. **Delete işleci** işlevi açıklandığı gibi erişim denetimi ilişkiden [üye erişim denetimi](../cpp/member-access-control-cpp.md).

Aşağıdaki örnek, kullanıcı tanımlı gösterir **new işleci** ve **delete işleci** ayırma ve bellek deallocations oturum için tasarlanmış İşlevler:

```cpp
// spec1_the_operator_delete_function1.cpp
// compile with: /EHsc
// arguments: 3
#include <iostream>
using namespace std;

int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?
int cBlocksAllocated = 0;  // Count of blocks allocated.

// User-defined operator new.
void *operator new( size_t stAllocateBlock ) {
   static int fInOpNew = 0;   // Guard flag.

   if ( fLogMemory && !fInOpNew ) {
      fInOpNew = 1;
      clog << "Memory block " << ++cBlocksAllocated
          << " allocated for " << stAllocateBlock
          << " bytes\n";
      fInOpNew = 0;
   }
   return malloc( stAllocateBlock );
}

// User-defined operator delete.
void operator delete( void *pvMem ) {
   static int fInOpDelete = 0;   // Guard flag.
   if ( fLogMemory && !fInOpDelete ) {
      fInOpDelete = 1;
      clog << "Memory block " << cBlocksAllocated--
          << " deallocated\n";
      fInOpDelete = 0;
   }

   free( pvMem );
}

int main( int argc, char *argv[] ) {
   fLogMemory = 1;   // Turn logging on
   if( argc > 1 )
      for( int i = 0; i < atoi( argv[1] ); ++i ) {
         char *pMem = new char[10];
         delete[] pMem;
      }
   fLogMemory = 0;  // Turn logging off.
   return cBlocksAllocated;
}
```

Yukarıdaki kod, "bellek sızıntısı" algılamak için kullanılabilir — diğer bir deyişle, ücretsiz mağaza ayrılmış ancak hiçbir zaman serbest bellek. Bu algılama, genel gerçekleştirmek için **yeni** ve **Sil** sayısı ayırma ve bellek ayırmayı kaldırma işleçleri yeniden tanımlandı.

Visual C++ 5.0 ile başlayan, derleyici üye dizisi destekler **yeni** ve **Sil** bir sınıf bildiriminde işleçleri. Örneğin:

```cpp
// spec1_the_operator_delete_function2.cpp
// compile with: /c
class X  {
public:
   void * operator new[] (size_t) {
      return 0;
   }
   void operator delete[] (void*) {}
};

void f() {
   X *pX = new X[5];
   delete [] pX;
}
```