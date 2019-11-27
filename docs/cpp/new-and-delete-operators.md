---
title: new ve delete İşleçleri
ms.date: 11/19/2019
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: c64b15f1e1e63b1e743743883429ffd11007de0a
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246444"
---
# <a name="new-and-delete-operators"></a>new ve delete işleçleri

C++, [New](new-operator-cpp.md) ve [Delete](delete-operator-cpp.md) işleçlerini kullanarak nesneleri dinamik ayırmayı ve ayırmayı destekler. Bu işleçler, serbest depo adlı bir havuzdan nesneler için bellek ayırır. **New** işleci [New](new-operator-cpp.md)özel Function işlecini çağırır ve **Delete** işleci özel işlev [işleci Delete](delete-operator-cpp.md)' i çağırır.

Standart kitaplıktaki **Yeni** işlev, C++ standart olarak belirtilen davranışı destekler; bu, bellek ayırma başarısız olursa std:: bad_alloc özel durumu oluşturur. C++ Henüz **Yeni**bir atma sürümü isterseniz, programınızı nothrownew. obj ile bağlayın. Ancak, nothrownew. obj ile bağladığınızda C++ standart kitaplıkta yeni olan varsayılan **işleç** artık çalışmaz.

C çalışma zamanı kitaplığını ve C++ standart kitaplığı oluşturan kitaplık dosyalarının listesi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

##  <a id="new_operator"></a> New işleci

Bir programda aşağıdakiler gibi bir ifadeye rastlandı, yeni bir işlev **işlecine**çağrı yapar:

```cpp
char *pch = new char[BUFFER_SIZE];
```

İstek sıfır baytlık depolama için ise, **New işleci** ayrı bir nesneye bir işaretçi döndürür (diğer bir deyişle, **Yeni işleç** için yinelenen çağrılar farklı işaretçiler döndürür). Ayırma isteği için yeterli bellek yoksa, **New işleci** `std::bad_alloc` bir özel durum oluşturur veya oluşturma olmayan **işlece yeni** destek ile bağlantı oluşturduysanız, **nullptr** döndürür.

Belleği boşaltmak ve ayırmayı yeniden denemek için bir yordam yazabilirsiniz; daha fazla bilgi için bkz. [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) . Kurtarma şeması hakkında daha fazla bilgi için bu konunun yetersiz bellek Işleme bölümüne bakın.

**İşleç yeni** işlevleri için iki kapsam aşağıdaki tabloda açıklanmıştır.

### <a name="scope-for-operator-new-functions"></a>New işleci işlevlerinin kapsamı

|İşleç|Kapsam|
|--------------|-----------|
|**:: New işleci**|Global|
|*class-name* **:: operator new**|Sınıf|

**New işlecine** yönelik ilk bağımsız değişken `size_t` türünde olmalıdır (\<stddef. h > ' de tanımlı bir tür) ve dönüş türü her zaman **void** <strong>\*</strong>.

**New** işleci, yerleşik türlerin nesnelerini, Kullanıcı tanımlı **işleç yeni** işlevleri içermeyen sınıf türü nesnelerini ve herhangi bir türdeki dizileri ayırmak için kullanıldığında, Yeni işleç **New** işlevi çağrılır. **New** işleci, **New işlecinin** tanımlandığı bir sınıf türünün nesnelerini ayırmak için kullanıldığında, bu sınıfın **New işleci** çağırılır.

Bir sınıf için tanımlanan **işleç yeni** işlevi, bir statik üye işlevidir (Bu nedenle, sanal olamaz) ve bu sınıf türünün nesneleri için genel **işleç yeni** işlevini gizler. Belleği ayırmak ve belirli bir değere ayarlamak için **Yeni** kullanılan durumu göz önünde bulundurun:

```cpp
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

Parantez içinde **New** olarak sağlanan bağımsız değişken `chInit` bağımsız değişkeni olarak `Blanks::operator new` geçirilir. Ancak, genel **operator new** işlevi gizlidir ve bir hata oluşturmak için aşağıdaki gibi kodun görüntülenmesine neden olur:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Derleyici, bir sınıf bildirimindeki üye dizisi **Yeni** ve **silme** işleçlerini destekler. Örneğin:

```cpp
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

Başarısız bellek ayırma testi, burada gösterildiği gibi yapılabilir:

```cpp
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

Başarısız bellek ayırma isteklerini işlemenin başka bir yolu vardır. Bu tür bir hatayı işlemek için özel bir kurtarma yordamı yazın ve ardından [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı işlevini çağırarak işlevinizi kaydedin.

##  <a id="delete_operator"></a> Delete işleci

**New** işleci kullanılarak dinamik olarak ayrılan bellek, **Delete** işleci kullanılarak serbest bırakılabilirler. Delete işleci, belleği kullanılabilir havuza yeniden **boşalten Delete işleç** işlevini çağırır. **Delete** işlecinin kullanılması Ayrıca sınıf yıkıcısına (varsa) neden olur.

Genel ve sınıf kapsamlı **işleç silme** işlevleri vardır. Belirli bir sınıf için yalnızca bir **işleç silme** işlevi tanımlanabilir; tanımlanmışsa, genel **işleç silme** işlevini gizler. Genel **işleç silme** işlevi her zaman bir türdeki diziler için çağırılır.

Genel **işleç silme** işlevi. Genel **işleç Delete** ve Class-member **işleci Delete** işlevleri için iki form mevcuttur:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Belirli bir sınıf için önceki iki formdan yalnızca biri bulunabilir. İlk form, serbest bırakma yapılacak nesneye bir işaretçi içeren `void *`türünde tek bir bağımsız değişken alır. İkinci form (boyutu kaldırma), ilki serbest bırakmak için bellek bloğunun bir işaretçisi olan iki bağımsız değişken alır ve ikincisi serbest bırakmak için gereken bayt sayısıdır. Her iki formun de dönüş türü **void** (**işleç Delete** bir değer döndüremez).

İkinci formun amacı, Silinecek nesnenin doğru boyut kategorisine yönelik aramayı hızlandırmaktır. Bu, genellikle tahsisatın yakınında depolanmamış ve muhtemelen önbelleğe alınmamış olabilir. İkinci form, türetilmiş bir sınıfın bir nesnesini silmek için temel sınıftan bir **işleç silme** işlevi kullanıldığında yararlıdır.

**İşleç silme** işlevi statiktir; Bu nedenle, sanal olamaz. **İşleç silme** Işlevi, [üye-Access Control](member-access-control-cpp.md)bölümünde açıklandığı gibi erişim denetimine uyar.

Aşağıdaki örnek, Kullanıcı tanımlı **New işlecini** ve bellek ayırmaları ve ayırmayı günlüğe kaydetmek için tasarlanan **işleç silme** işlevlerini göstermektedir:

```cpp
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

Yukarıdaki kod, "bellek sızıntısı", diğer bir deyişle, ücretsiz depoya ayrılan ancak hiç boşaltılmamış bellek algılamak için kullanılabilir. Bu algılamayı gerçekleştirmek için, genel **Yeni** ve **silme** işleçleri, belleğin ayrılması ve ayırmayı kaldırma için yeniden tanımlanır.

Derleyici, bir sınıf bildirimindeki üye dizisi **Yeni** ve **silme** işleçlerini destekler. Örneğin:

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
