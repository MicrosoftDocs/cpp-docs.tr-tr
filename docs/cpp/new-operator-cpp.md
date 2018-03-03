---
title: "New işleci (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68843f0619b5ebc057f83bdb4f49807a15fb86a1
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="new-operator-c"></a>new İşleci (C++)
Bir nesne ya da dizi nesneleri için bellek ayırır *türü adı* boş depolamak ve uygun yazılan, sıfır olmayan bir işaretçi nesneyi döndürür.  
  
> [!NOTE]
>  Microsoft C++ bileşen uzantıları için destek sağlar `new` vtable yuvası girdileri eklemek için anahtar sözcüğü. Daha fazla bilgi için bkz: [yeni (vtable'de yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşlem başarısız olursa, **yeni** döndürür sıfır veya bir özel durum oluşturur; bkz [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md) daha fazla bilgi için. Bir özel durum işleme yordamına yazma ve arama bu varsayılan davranışı değiştirebilirsiniz [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı kitaplığı işlevi bağımsız değişken olarak işlevi adınız ile.  
  
 Yönetilen yığında bir nesne oluşturma hakkında daha fazla bilgi için bkz: [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
 Zaman **yeni** olan bir C++ sınıf nesnesi için bellek tahsis için kullanılan bellek tahsis sonra nesnenin oluşturucusu çağrılır.  
  
 Kullanım [silmek](../cpp/delete-operator-cpp.md) operatörü ile ayrılan bellek ayırması **yeni** işleci.  
  
 Aşağıdaki örnek ayırır ve karakter sayısını boyutu iki boyutlu bir dizi boşaltır `dim` 10 tarafından. Çok boyutlu bir diziye ayırırken hariç tüm boyutları pozitif değerlere değerlendirmek sabit ifadeleri olmalıdır; Soldaki dizi boyutu pozitif bir değer veren herhangi bir ifade olabilir. Kullanarak bir dizinin ayırırken **yeni** işleci, ilk boyutu sıfır olabilir — **yeni** işleci benzersiz bir işaretçi döndürür.  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 *Türü adı* içeremez **const**, `volatile`, sınıf bildirimleri veya numaralandırma bildirimleri. Bu nedenle, aşağıdaki ifade geçersiz:  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 **Yeni** işleci ayrılamadı başvuru türleri nesneleri olmadıklarından.  
  
 **Yeni** işleci, bir işlev ayırmak için kullanılamaz, ancak işlev işaretçileri ayırmak için kullanılabilir. Aşağıdaki örnek ayırır ve yedi işaretçileri tamsayılar döndüren işlevler için bir dizi boşaltır.  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 İşleç kullanırsanız **yeni** tüm ek bağımsız değişkenler ve derleme ile olmadan [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md), veya [/EHs](../build/reference/eh-exception-handling-model.md) derleyici seçeneği olur işleç çağırmak için kodu oluşturmak **silmek** Oluşturucusu bir özel durum oluşturursa.  
  
 Aşağıdaki liste dilbilgisi öğelerini açıklar **yeni**:  
  
 *yerleştirme*  
 Aşırı yükleme varsa ek bağımsız değişkenler geçirme bir yol sağlayan **yeni**.  
  
 *tür adı*  
 Ayrılacak türünü belirtir; Yerleşik veya kullanıcı tanımlı türü olabilir. Tür belirtimi karmaşık ise, bağlama sırasını zorlamak için parantez ile çevrelenmiş.  
  
 *initializer*  
 Başlatılmış bir nesne için bir değer sağlar. Başlatıcılar diziler için belirtilemez. **Yeni** işleci yalnızca sınıfı varsayılan bir oluşturucu varsa nesne dizileri oluşturur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir karakter dizisi ve sınıfın bir nesnesi ayırır `CName` ve bunları boşaltır.  
  
```  
// expre_new_Operator.cpp  
// compile with: /EHsc  
#include <string.h>  
  
class CName {  
public:  
   enum {  
      sizeOfBuffer = 256  
   };  
  
   char m_szFirst[sizeOfBuffer];  
   char m_szLast[sizeOfBuffer];  
  
public:  
   void SetName(char* pszFirst, char* pszLast) {  
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);  
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);  
   }  
  
};  
  
int main() {  
   // Allocate memory for the array  
   char* pCharArray = new char[CName::sizeOfBuffer];  
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");  
  
   // Deallocate memory for the array  
   delete [] pCharArray;             
   pCharArray = NULL;  
  
   // Allocate memory for the object  
   CName* pName = new CName;  
   pName->SetName("Firstname", "Lastname");  
  
   // Deallocate memory for the object  
   delete pName;  
   pName = NULL;  
}  
```  
  
## <a name="example"></a>Örnek  
 Yerleştirme yeni biçiminde kullanırsanız **yeni** işleci, derleyici ayırma boyutu yanı sıra bağımsız değişkenlerle biçiminde yerleştirme biçimi desteklemiyor **silmek** işleci varsa Oluşturucusu bir özel durum oluşturur. Örneğin:  
  
```  
// expre_new_Operator2.cpp  
// C2660 expected  
class A {  
public:  
   A(int) { throw "Fail!"; }  
};  
void F(void) {  
   try {  
      // heap memory pointed to by pa1 will be deallocated  
      // by calling ::operator delete(void*).  
      A* pa1 = new A(10);  
   } catch (...) {  
   }  
   try {  
      // This will call ::operator new(size_t, char*, int).  
      // When A::A(int) does a throw, we should call  
      // ::operator delete(void*, char*, int) to deallocate  
      // the memory pointed to by pa2.  Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
  
      A* pa2 = new(__FILE__, __LINE__) A(20);  
   } catch (...) {  
   }  
}  
  
int main() {  
   A a;  
}  
```  
  
## <a name="initializing-object-allocated-with-new"></a>New ile ayrılmış nesnesi başlatma  
 İsteğe bağlı bir *Başlatıcı* alan için dilbilgisi dahil **yeni** işleci. Bu, kullanıcı tanımlı oluşturucularla yeni nesnelerin başlatılmasını sağlar. Başlatma nasıl yapılacağı hakkında daha fazla bilgi için bkz: [başlatıcıları](../cpp/initializers.md). Aşağıdaki örnek bir başlatma deyimiyle kullanma gösterilmektedir **yeni** işleci:  
  
```  
// expre_Initializing_Objects_Allocated_with_new.cpp  
class Acct  
{  
public:  
    // Define default constructor and a constructor that accepts  
    //  an initial balance.  
    Acct() { balance = 0.0; }  
    Acct( double init_balance ) { balance = init_balance; }  
private:  
    double balance;  
};  
  
int main()  
{  
    Acct *CheckingAcct = new Acct;  
    Acct *SavingsAcct = new Acct ( 34.98 );  
    double *HowMuch = new double ( 43.0 );  
    // ...  
}  
```  
  
 Bu örnekte, nesne `CheckingAcct` kullanılarak ayrılmış **yeni** işleci, ancak hiçbir varsayılan başlatma belirtilir. Bu nedenle, `Acct()` sınıfı için varsayılan oluşturucu çağrılır. Ardından `SavingsAcct` nesnesi aynı şekilde ayrılır, ancak açıkça 34.98'e başlatılır. 34.98 türünde olduğundan **çift**, o türünde bir bağımsız değişken alan oluşturucusu başlatma işlemek için çağrılır. Son olarak, `HowMuch` nonclass türü 43.0 için başlatılır.  
  
 Tarafından bir sınıf türünde bir nesne ve bu sınıf oluşturucular (önceki örnekte olduğu gibi) varsa, nesne başlatılabilir **yeni** yalnızca bu koşullardan biri karşılandığında işleci:  
  
-   Başlatıcıda sağlanan bağımsız değişkenler oluşturucununkilerle uyumludur.  
  
-   Sınıfın varsayılan bir oluşturucusu (bağımsız değişken olmadan çağrılabilecek bir oluşturucu) vardır.  
  
 Ayırma diziler kullanarak hiçbir açık öğesi başına başlatma yapılabilir **yeni** işleci; yalnızca varsayılan oluşturucu varsa, adı verilir. Bkz: [varsayılan bağımsız değişkenler](../cpp/default-arguments.md) daha fazla bilgi için.  
  
 Bellek ayırma başarısız olursa (`operator new` 0 değerini döndürür), hiçbir başlatma gerçekleştirilmez. Bu, var olmayan verileri başlatma girişimlerini önler.  
  
 İşlev çağrılarında olduğu gibi, başlatılan ifadelerin değerlendirilme sırası tanımlı değildir. Ayrıca, bellek ayırma işlemi yapılmadan önce bu ifadelerin tamamen değerlendirileceğine güvenmemelisiniz. Bellek ayırma başarısız olursa ve **yeni** işleci sıfır döndürür, başlatıcı bazı ifadelerinde değil tamamen değerlendirilmesi.  
  
## <a name="lifetime-of-objects-allocated-with-new"></a>New ile ayrılmış nesnelerin ömrü  
 İle ayrılmış nesneleri **yeni** bunlar tanımlanan kapsam çıkıldı olduğunda, işleci yok değil. Çünkü **yeni** işleci ayırdığı nesneleri için bir işaretçi döndürür, programın bu nesnelere erişmek için uygun kapsama sahip bir işaretçi tanımlamanız gerekir. Örneğin:  
  
```  
// expre_Lifetime_of_Objects_Allocated_with_new.cpp  
// C2541 expected  
int main()  
{  
    // Use new operator to allocate an array of 20 characters.  
    char *AnArray = new char[20];  
  
    for( int i = 0; i < 20; ++i )  
    {  
        // On the first iteration of the loop, allocate  
        //  another array of 20 characters.  
        if( i == 0 )  
        {  
            char *AnotherArray = new char[20];  
        }  
    }  
  
    delete [] AnotherArray; // Error: pointer out of scope.  
    delete [] AnArray;      // OK: pointer still in scope.  
}  
```  
  
 `AnotherArray` işaretçisi örnekteki kapsamdan çıktığında, nesne artık silinemez.  
  
## <a name="how-new-works"></a>New nasıl çalışır  
 *Ayırma ifade* — ifadesi içeren **yeni** işleci — üç şey yapar:  
  
-   Bulur ve nesneyi ya da ayrılacak nesneleri için depolama ayırır. Bu aşaması tamamlandıktan sonra depolama doğru miktarı ayrılmış, ancak henüz bir nesne değil.  
  
-   Nesneleri başlatır. Başlatma tamamlandıktan sonra bir nesne ayrılan depolama alanı için yeterli bilgi yok.  
  
-   İşaretçi türü nesneleri için bir işaretçi türetilen döndürür *türü adı yeni* veya *türü adı*. Program bu işaretçinin yeni ayrılan nesnesine erişmek için kullanır.  
  
 **Yeni** işleci işlevi çağırır `operator new`. Olmayan nesneler ve diziler herhangi bir tür için **sınıfı**, `struct`, veya **UNION** türleri, global işlevi **:: işleci yeni**, depolama alanı ayırmak için çağrılır. Sınıf türü nesneleri tanımlayabilirsiniz, kendi `operator new` sınıfı başına temelinde statik üye işlevi.  
  
 Derleyici karşılaştığında **yeni** türünde bir nesne ayrılamadı işleci `type`, çağrı sorunları `type` **:: new işleci (sizeof (** `type` **))**  veya kullanıcı tanımlı Hayır ise `operator new` tanımlanan **:: new işleci (sizeof (** `type` **))**. Bu nedenle, **yeni** işleci, nesne için doğru bellek miktarını ayırabilirsiniz.  
  
> [!NOTE]
>  Bağımsız değişkeni `operator new` türü **size_t**. Bu tür tanımlanan \<direct.h >, \<malloc.h >, \<memory.h >, \<search.h >, \<stddef.h >, \<stdio.h >, \<stdlib.h >, \<string.h >, ve \<time.h >.  
  
 Dilbilgisi bir seçenek belirtimi verir *yerleştirme* (dil bilgisi için bkz: [new işleci](../cpp/new-operator-cpp.md)). *Yerleştirme* parametresi yalnızca kullanıcı tanımlı uygulamaları için kullanılabilir `operator new`; geçirilecek ek bilgiler sağlayan `operator new`. Bir ifade içeren bir *yerleştirme* gibi alan `T *TObject = new ( 0x0040 ) T;` için çevrilen `T *TObject = T::operator new( sizeof( T ), 0x0040 );` sınıfı T üye işleci yeni, aksi takdirde gerekiyorsa `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.  
  
 Özgün amacı *yerleştirme* alan olan kullanıcı tarafından belirtilen adreslerde ayrılacak donanım bağımlı nesneleri izin vermek için.  
  
> [!NOTE]
>  Önceki örnekte, yalnızca tek bir bağımsız değişken gösterir, ancak *yerleştirme* alan, kaç tane ek bağımsız değişkenler için geçirilebilir üzerinde sınırlaması yoktur `operator new` bu şekilde.  
  
 Zaman bile `operator new` tanımlanmış bir sınıf türü için bu örnek formunu kullanarak genel işleci kullanılabilir:  
  
```  
T *TObject =::new TObject;  
```  
  
 Kapsam çözümü işleci (`::`) zorlar genel kullanımını **yeni** işleci.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Yeni ve delete işleçleri](../cpp/new-and-delete-operators.md)