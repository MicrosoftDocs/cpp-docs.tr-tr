---
title: new ve delete İşleçleri
ms.date: 11/19/2019
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: fd170c1500e2d80879fdd89f7d825930189ae942
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367883"
---
# <a name="new-and-delete-operators"></a>new ve delete işleçleri

C++, [yeni](new-operator-cpp.md) ve [sil](delete-operator-cpp.md) işleçlerini kullanarak nesnelerin dinamik tahsisini ve deallocation'sini destekler. Bu işleçler, boş depo adı verilen bir havuzdaki nesneler için bellek ayırır. **Yeni** işleç özel işlev [işleci](new-operator-cpp.md)yeni çağırır ve **silme** işleci özel işlev [işleci silmek](delete-operator-cpp.md)çağırır.

C++ Standart Kitaplığı'ndaki **yeni** işlev, C++ standardında belirtilen davranışı destekler, bu da bellek ayırma başarısız olursa bad_alloc özel durum oluşturur. Hala **yeni**olmayan atma sürümü istiyorsanız, nothrownew.obj ile programı bağlantı. Ancak, nothrownew.obj ile bağlantı yaptığınızda, C++ Standart Kitaplığı'nda yeni varsayılan **işleç** artık çalışmıyor.

C Runtime Kitaplığı ve C++ Standart Kitaplığı'nı oluşturan kitaplık dosyalarının listesi için [CRT Kitaplık Özellikleri'ne](../c-runtime-library/crt-library-features.md)bakın.

## <a name="the-new-operator"></a><a id="new_operator"> </a> Yeni operatör

Bir programda aşağıdaki gibi bir ifadeyle karşılaşıldığında, işlev **işlecinin yeni**bir çağrısına dönüşür:

```cpp
char *pch = new char[BUFFER_SIZE];
```

İstek sıfır bayt depolama alanı içinse, **işleç yeni** bir işaretçiyi farklı bir nesneye döndürür (diğer bir süre önce **işleç için** yinelenen çağrılar yeni farklı işaretçileri döndürür). Ayırma isteği için yeterli bellek yoksa, **operatör** `std::bad_alloc` yeni bir özel durum atar veya atmayan **işleç yeni** destek bağlı varsa **nullptr** döndürür.

Belleği serbest bırakıp ayırmayı yeniden denemeye çalışan bir yordam yazabilirsiniz; daha fazla bilgi için [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) bakın. Kurtarma düzeni hakkında daha fazla bilgi için, bu konunun Yetersiz Bellek Kullanma bölümüne bakın.

**Operatör yeni** işlevleri için iki kapsam aşağıdaki tabloda açıklanmıştır.

### <a name="scope-for-operator-new-functions"></a>Operatör yeni işlevleri için kapsam

|İşleç|Kapsam|
|--------------|-----------|
|**::operatör yeni**|Genel|
|*sınıf adı* **::operatör yeni**|Sınıf|

Yeni **işleç** için ilk bağımsız `size_t` değişken türü \<(stddef.h> tanımlanan bir tür) olmalıdır ve dönüş türü her zaman **geçersizdir.** <strong>\*</strong>

Yeni **işleç,** yerleşik türlerin, kullanıcı tanımlı **işleç yeni** işlevleri içermeyen sınıf türü nesneleri ve herhangi bir türdeki dizileri ayırmak için kullanıldığında, global **işleç yeni** işlevi olarak adlandırılır. **Yeni** **işleç, yeni** bir işleç tanımlandığı bir sınıf türündeki nesneleri ayırmak için kullanıldığında, sınıfın **yeni işleci** çağrılır.

Bir sınıf için tanımlanan **işleç yeni** işlevi, bu sınıf türündeki nesneler için global **işleç yeni** işlevini gizleyen statik bir üye işlevdir (bu nedenle sanal olamaz). **Yeninin** belirli bir değere bellek ayırmak ve ayarlamak için kullanıldığı durumu göz önünde bulundurun:

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

Parantez içinde **yeniye** verilen `chInit` bağımsız değişken `Blanks::operator new` bağımsız değişken olarak aktarılır. Ancak, global **işleç yeni** işlev gizlidir ve aşağıdaki gibi kodlar bir hata oluşturmak için neden olur:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Derleyici, bir sınıf bildiriminde üye dizi **yeni** ve **silme** işleçleri destekler. Örneğin:

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

Başarısız bellek ayırma için sınama burada gösterildiği gibi yapılabilir:

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

Başarısız bellek ayırma isteklerini işlemenin başka bir yolu daha vardır. Böyle bir hatayı işlemek için özel bir kurtarma yordamı yazın ve [ardından _set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı işlevini çağırarak işlevinizi kaydedin.

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> Silme işleci

**Yeni** işleç kullanılarak dinamik olarak ayrılan bellek **silme** işleci kullanılarak serbest bırakılabilir. Silme işleci, belleği kullanılabilir havuza geri boşaltan **işleç silme** işlevini çağırır. **Silme** işlecinin kullanılması, sınıf yıkıcısının (varsa) çağrılmasını da neden olur.

Genel ve sınıf kapsamlı **işleç silme** işlevleri vardır. Belirli bir sınıf için yalnızca bir **operatör silme** işlevi tanımlanabilir; tanımlanırsa, genel **işleç silme** işlevini gizler. Global **işleç silme** işlevi her zaman herhangi bir türdeki diziler için çağrılır.

Genel **işleç silme** işlevi. Global **işleç silme** ve sınıf üyesi **işleç silme** işlevleri için iki form vardır:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Belirli bir sınıf için önceki iki formdan yalnızca biri bulunabilir. İlk form, anlaşma için `void *`nesneye işaretçi içeren tek bir tür bağımsız değişkeni alır. İkinci form boyutlu deallocation-iki bağımsız değişken alır, bunlardan ilki anlaşma için bellek bloğuna bir işaretçi ve ikincisi işlem için bayt sayısıdır. Her iki formun dönüş türü **geçersizdir** **(işleç silme** bir değer döndüremez).

İkinci formun amacı, silinecek nesnenin doğru boyut kategorisini aramayı hızlandırmaktır ve bu kategori genellikle ayırmanın yakınında depolanmaz ve büyük olasılıkla cached edilmemiştir. İkinci form, türemiş bir sınıfın nesnesini silmek için bir **işleç işlevi** taban sınıftan silindiğinde yararlıdır.

**Operatör silme** işlevi statiktir; bu nedenle, sanal olamaz. **Operatör silme** işlevi, [Üye-Erişim Denetimi'nde](member-access-control-cpp.md)açıklandığı gibi erişim denetimine uyar.

Aşağıdaki örnek, kullanıcı tanımlı **işleç yeni** ve **operatör silme** işlevlerini bellek tahsisatlarını ve anlaşma konumlarını günlüğe kaydetmek için tasarlanmış olarak gösterir:

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

Önceki kod "bellek sızıntısı" algılamak için kullanılabilir - yani, serbest depoya ayrılan ancak asla serbest asla bellek. Bu algılamayı gerçekleştirmek için, genel **yeni** ve **silme** işleçleri, bellek tahsisatını ve deallocation'sini saymak için yeniden tanımlanır.

Derleyici, bir sınıf bildiriminde üye dizi **yeni** ve **silme** işleçleri destekler. Örneğin:

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
