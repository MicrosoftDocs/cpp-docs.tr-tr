---
title: new ve delete işleçleri
description: New ve delete işleçleri C++ dili ayırma üzerinde denetime izin verir.
ms.date: 07/07/2020
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.openlocfilehash: e609d1fdbd4f945ab8709c554d1396100027c4c1
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127846"
---
# <a name="new-and-delete-operators"></a>`new`ve `delete` işleçleri

C++, ve işleçlerini kullanarak nesneleri dinamik ayırmayı ve ayırmayı [`new`](new-operator-cpp.md) destekler [`delete`](delete-operator-cpp.md) . Bu işleçler, serbest depo adlı bir havuzdan nesneler için bellek ayırır. **`new`** İşleci özel işlevi çağırır [`operator new`](new-operator-cpp.md) ve **`delete`** işleç özel işlevi çağırır [`operator delete`](delete-operator-cpp.md) .

**`new`** C++ standart kitaplığı 'ndaki işlevi, c++ standardında belirtilen davranışı destekler, bu da `std::bad_alloc` bellek ayırma başarısız olursa bir özel durum oluşturur. ' In oluşturmama ait olmayan sürümünü istiyorsanız **`new`** , programınızı ile bağlayın *`nothrownew.obj`* . Ancak, ile bağlantı oluşturduğunuzda *`nothrownew.obj`* , **`operator new`** C++ standart kitaplığı 'ndaki varsayılan değer artık çalışmaz.

C çalışma zamanı kitaplığı ve C++ standart kitaplığı 'ndaki kitaplık dosyalarının listesi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

## <a name="the-new-operator"></a><a id="new_operator"> </a> `new` İşleci

Derleyici, bu gibi bir ifadeyi işleve yapılan çağrıya çevirir **`operator new`** :

```cpp
char *pch = new char[BUFFER_SIZE];
```

İstek sıfır baytlık depolama için ise, **`operator new`** ayrı bir nesneye bir işaretçi döndürür. Diğer bir deyişle, **`operator new`** farklı işaretçiler döndürmek için yinelenen çağrılar. Ayırma isteği için yeterli bellek yoksa **`operator new`** bir `std::bad_alloc` özel durum oluşturur. Ya da, oluşturma **`nullptr`** olmayan destek ile bağlantılandırdıysanız, döndürür **`operator new`** .

Belleği boşaltmak ve ayırmayı yeniden denemek için bir yordam yazabilirsiniz. Daha fazla bilgi için bkz. [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md). Kurtarma şeması hakkında daha fazla bilgi için, [yetersiz bellek işleme](#handling-insufficient-memory) bölümüne bakın.

İşlevleri için iki kapsam **`operator new`** Aşağıdaki tabloda açıklanmıştır.

### <a name="scope-for-operator-new-functions"></a>İşlevler için kapsam `operator new`

| Operatör | Kapsam |
|--|--|
| **`::operator new`** | Genel |
| *sınıf adı***`::operator new`** | Sınıf |

İçin ilk bağımsız değişken **`operator new`** türünde olması gerekir `size_t` , öğesinde tanımlanır \<stddef.h> ve dönüş türü her zaman olur **`void*`** .

Genel **`operator new`** işlevi, **`new`** işleç yerleşik türlerin nesnelerini, Kullanıcı tanımlı işlevleri içermeyen sınıf türü nesnelerini **`operator new`** ve herhangi bir türdeki dizileri ayırmak için kullanıldığında çağrılır. İşleci, **`new`** tanımlanan bir sınıf türünün nesnelerini ayırmak için kullanıldığında **`operator new`** , bu sınıf **`operator new`** çağrılır.

**`operator new`** Sınıf için tanımlanan bir işlev, **`operator new`** Bu sınıf türündeki nesneler için genel işlevi gizleyen statik bir üye işlevidir (sanal olamaz). **`new`** Verilen bir değere bellek ayırmak ve ayarlamak için kullanılan durumu göz önünde bulundurun:

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

Parantez içinde sağlanan bağımsız değişken, **`new`** `Blanks::operator new` bağımsız değişken olarak öğesine geçirilir `chInit` . Ancak, genel **`operator new`** işlev gizlidir ve bir hata oluşturmak için aşağıdaki gibi kodun görüntülenmesine neden olur:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Derleyici, **`new`** **`delete`** bir sınıf bildiriminde üye dizisini ve işleçleri destekler. Örneğin:

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

Başarısız bellek ayırma isteklerini işlemenin başka bir yolu vardır. Bu tür bir hatayı işlemek için özel bir kurtarma yordamı yazın ve ardından çalışma zamanı işlevini çağırarak işlevinizi kaydedin [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md) .

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> `delete` İşleci

İşleci kullanılarak dinamik olarak ayrılan bellek **`new`** , işleci kullanılarak serbest bırakılabilirler **`delete`** . Delete işleci, **`operator delete`** belleği kullanılabilir havuza geri boşalten işlevini çağırır. İşleci kullanmak **`delete`** Ayrıca sınıf yıkıcısına (varsa) neden olur.

Genel ve sınıf kapsamlı **`operator delete`** işlevler vardır. **`operator delete`** Belirli bir sınıf için yalnızca bir işlev tanımlanabilir; tanımlanmışsa, genel **`operator delete`** işlevi gizler. Genel **`operator delete`** işlev her zaman bir türdeki diziler için çağırılır.

Genel **`operator delete`** işlev. Genel **`operator delete`** ve sınıf üye işlevleri için iki form mevcuttur **`operator delete`** :

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Belirli bir sınıf için önceki iki formdan yalnızca biri bulunabilir. İlk form **`void *`** , serbest bırakma yapılacak nesneye bir işaretçi içeren türünde tek bir bağımsız değişken alır. Boyutu kaldırılacak ikinci form, iki bağımsız değişkeni alır: Birincisi, bellek bloğunun serbest olması için bir işaretçidir ve ikincisi serbest bırakma için bayt sayısıdır. Her iki formun de dönüş türü **`void`** ( **`operator delete`** değer döndüremez).

İkinci formun amacı, Silinecek nesnenin doğru boyut kategorisini aramayı hızlandırmaktır. Bu bilgiler genellikle ayırcının yakınında depolanmaz ve muhtemelen önbelleğe alınmamış olabilir. İkinci form, türetilmiş bir sınıfın bir **`operator delete`** nesnesini silmek için temel sınıftan bir işlev kullanıldığında yararlıdır.

**`operator delete`** İşlev statiktir, bu nedenle sanal olamaz. **`operator delete`** İşlev, [üye Access Control](member-access-control-cpp.md)bölümünde açıklandığı gibi erişim denetimine uyar.

Aşağıdaki örnek, Kullanıcı tanımlı **`operator new`** ve **`operator delete`** bellek ayırmayı günlüğe kaydetmek için tasarlanan işlevleri gösterir:

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

Yukarıdaki kod, "bellek sızıntısı", diğer bir deyişle, ücretsiz depoya ayrılan ancak hiç boşaltılmamış bellek algılamak için kullanılabilir. Sızıntıları tespit etmek için genel **`new`** ve **`delete`** işleçler, belleğin ayrılması ve ayırmayı kaldırma için yeniden tanımlanır.

Derleyici, **`new`** **`delete`** bir sınıf bildiriminde üye dizisini ve işleçleri destekler. Örneğin:

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
