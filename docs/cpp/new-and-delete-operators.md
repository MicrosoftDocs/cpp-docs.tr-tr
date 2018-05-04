---
title: Yeni ve delete işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- delete_cpp
- new
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7f411d05491294421202ae6d8a1b7cbbb4e1d47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="new-and-delete-operators"></a>new ve delete İşleçleri

Dinamik ayırma ve ayırmayı kaldırma kullanarak nesnelerin C++ destekler [yeni](../cpp/new-operator-cpp.md) ve [silmek](../cpp/delete-operator-cpp.md) işleçler. Bu işleçlere ücretsiz deposu olarak adlandırılan bir havuzdan nesneler için bellek tahsis. `new` İşleci özel işlevi çağırır [new işleci](../cpp/new-operator-cpp.md)ve `delete` işleci özel işlevi çağırır [delete işleci](../cpp/delete-operator-cpp.md).  
  
 `new` İşlevi C++ Standart Kitaplığı'nda Bellek ayırma başarısız olursa std::bad_alloc özel durum oluşturmaktır C++ Standart belirtilen davranışı destekler. Hala atma olmayan sürümü istiyorsanız `new`, nothrownew.obj programınızla bağlantı. Ancak, varsayılan nothrownew.obj ile bağladığınızda `operator new` C++ Standart Kitaplığı'nda artık çalışmaz.  
  
 C çalışma zamanı kitaplığı ve C++ Standart Kitaplığı oluşturan kitaplığı dosyaların listesi için bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
##  <a id="new_operator"> </a> New işleci  
 Bir programda aşağıdaki gibi bir deyimle karşılaşıldığında, `operator new` işlevinin çağrısına çevrilir:  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
İstek için depolama sıfır bayt ise **new işleci** ayrı bir nesneye bir işaretçi döndürür (diğer bir deyişle, çağrıları yinelenen **new işleci** farklı işaretçiler döndüren). Yetersiz bellek ayırma isteği için ise **new işleci** std::bad_alloc özel durum oluşturur ya da döndürür **nullptr** içinde olmayan atma bağladıysanız `operator new` destekler.  
  
Bellek boşaltın ve ayırmayı yeniden deneme girişiminde bir yordam yazabilirsiniz; bkz: [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) daha fazla bilgi için. Kurtarma şeması hakkında daha fazla bilgi için bu konuda işleme yetersiz bellek bölümüne bakın.  

  
`operator new` işlevlerine yönelik iki kapsam, aşağıdaki tabloda açıklanmıştır.  
  
### <a name="scope-for-operator-new-functions"></a>new işleci işlevlerine yönelik kapsam  
  
|İşleç|Kapsam|  
|--------------|-----------|  
|**:: new işleci**|Global|  
|*sınıf adı* **:: new işleci**|örneği|  
  
 İlk bağımsız değişken **new işleci** türünde olmalıdır **size_t** (tanımlanan bir türü \<stddef.h >), ve dönüş türü her zaman **void \***  .  
  
 Genel **new işleci** işlevi çağrılır **yeni** işleci, yerleşik türlerin ayırmak için kullanılır, içermeyen nesneleri sınıf türü kullanıcı tanımlı **new işleci** işlevler ve diziler herhangi bir türde. Zaman **yeni** işleci nesneleri sınıf türü ayırmak için kullanılan burada bir **new işleci** tanımlanır, o sınıfın **new işleci** olarak adlandırılır.  
  
 Bir **new işleci** bir sınıf genel gizleyen (Bu nedenle, sanal olamaz) bir statik üye işlevi için tanımlanan işlevi **new işleci** işlevi bu sınıf türündeki nesneler için. Bir durum düşünün nerede **yeni** ayırmak ve bellek belirli bir değere ayarlamak için kullanılır:  
  
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
  
 Parantez sağlanan bağımsız değişken **yeni** geçirilir `Blanks::operator new` olarak `chInit` bağımsız değişkeni. Ancak, genel **new işleci** işlevi gizli, bir hata oluşturmak için aşağıdaki gibi kod neden:  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 Visual C++ 5.0 ve önceki nonclass türleri ve tüm diziler (biri oldukları bağımsız olarak **sınıfı** türü) kullanılarak ayrılmış **yeni** işleci her zaman kullanılan genel **new işleci** işlevi.  
  
 Visual C++ 5.0 ile başlayarak, derleyici üye dizi destekleyen **yeni** ve **silmek** sınıf bildirimindeki işleçler. Örneğin:  
  
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
  
 Başarısız bellek ayırma isteklerini işlemek için başka bir yolu yoktur: Böyle bir hata işlemek için bir özel kurtarma yordamı yazma ve işlevinizi çağırarak kaydedin [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı işlevi.  
  
##  <a id="delete_operator"> </a> Delete işleci  
 Kullanarak dinamik olarak ayrılan bellek **yeni** işleci kullanılarak serbest bırakılmış **silmek** işleci. Delete işleci çağrıları **delete işleci** bellek kullanılabilir havuzuna serbest bırakma işlevi. Kullanarak **silmek** işleci ayrıca neden olur. sınıf yıkıcı (varsa) çağrılabilir.  
  
 Genel ve sınıf kapsamlı **delete işleci** işlevleri. Yalnızca bir **delete işleci** işlevi için belirli bir sınıfın tanımlanabilir; tanımlanmışsa, genel gizler **delete işleci** işlevi. Genel **delete işleci** işlevi herhangi bir tür diziler için her zaman çağrılır.  
  
 Genel **delete işleci** işlevi. İki tür genel için mevcut **delete işleci** ve sınıf üyesi **delete işleci** işlevleri:  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Önceki iki forms yalnızca biri için belirli bir sınıfın var olabilir. Tek bir bağımsız değişken türü ilk biçimdedir **void \*** , serbest bırakma nesnesine bir işaretçi içeriyor. İkinci form — ayırmayı kaldırma boyutta — ilki ayırması için bellek bloğu için bir işaretçi ve ikinci ayırması bayt sayısı iki bağımsız değişkeni alır. Her iki forms dönüş türü `void` (**delete işleci** bir değer döndüremiyor).  
  
 İkinci form amacı, genelde ayırma depolanır ve büyük olasılıkla Histogramı Silinecek nesnenin doğru boyutta kategori için arama yedeklemek için hızıdır; İkinci form özellikle yararlı olduğunda bir **delete işleci** işlevi temel sınıfından türetilen bir sınıftan bir nesneyi silmek için kullanılır.  
  
 **Delete işleci** işlevi statik; bu nedenle, sanal olamaz. `operator delete` İşlevi açıklandığı gibi erişim denetimi, obeys [üye erişim denetimi](../cpp/member-access-control-cpp.md).  
  
 Aşağıdaki örnek, kullanıcı tanımlı gösterir **new işleci** ve **delete işleci** oturum ayırmaları ve bellek ayırma kaldırma işlemleri için tasarlanmış işlevleri:  
  
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
  
 Önceki kod "bellek sızıntısı" algılamak için kullanılan — diğer bir deyişle, ücretsiz deponuzu ayrılmış olan, ancak hiçbir zaman serbest bellek. Bu algılama, genel gerçekleştirmek için **yeni** ve **silmek** sayısı ayırma ve bellek ayırmayı kaldırma işleçleri yeniden tanımlandı.  
  
 Visual C++ 5.0 ile başlayarak, derleyici üye dizi destekleyen **yeni** ve **silmek** sınıf bildirimindeki işleçler. Örneğin:  
  
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

