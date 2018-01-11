---
title: const (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: const_cpp
dev_langs: C++
helpviewer_keywords: const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c296f473f9128907e69437edf66734a7566242ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="const-c"></a>const (C++)
Bir veri bildirimi değiştirirken **const** anahtar sözcüğü nesne veya değişken değiştirilebilir olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>sabit değerler  
 **Const** anahtar sözcüğü bir değişkenin değeri sabittir ve Programcı bunu değiştirmesine engel olmaya derleyici söyler belirtir.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 C++'da, kullandığınız **const** anahtar sözcüğü yerine [#define](../preprocessor/hash-define-directive-c-cpp.md) sabit değerleri tanımlamak için önişlemci yönergesi. İle tanımlanan değerleri **const** tür denetlemesi tabi olan ve sabit ifadeler yerine kullanılabilir. C++'da, bir dizi boyutu belirtebilirsiniz bir **const** şekilde değişkeni:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 C, dış bağlantı için sabit değerler varsayılan olarak bu nedenle bunlar yalnızca kaynak dosyalarında yer alabilir. C++, sabit değerler varsayılan iç bağlantı için hangi üstbilgi dosyalarında görünmesini sağlar.  
  
 **Const** anahtar sözcüğü işaretçi bildirimleri de kullanılabilir.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Bir işaretçi olarak bildirilen bir değişken **const** de olarak bildirilen bir işaretçi atanmış **const**.  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 İşlev işaretçisi geçirilen parametre değiştirmesini önlemek için sabit veri işaretçileri işlevi parametre olarak kullanabilirsiniz.  
  
 Olarak bildirilen nesneler için **const**, yalnızca sabit üye işlevleri çağırabilir. Bu sabit nesne hiçbir zaman değişiklik sağlar.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Nonconstant bir nesne için sabit veya nonconstant üye işlevleri çağırabilirsiniz. Üye işlevini kullanarak da aşırı yüklenebilir **const** anahtar sözcüğü; bu sabit ve nonconstant nesneler için çağrılacak işlev farklı bir sürümünü sağlar.  
  
 Oluşturucular veya Yıkıcılar ile bildiremezsiniz **const** anahtar sözcüğü.  
  
## <a name="const-member-functions"></a>sabit üye işlevleri  
 Üye işlevi ile bildirme **const** anahtar sözcüğü işlevi için adlandırılan nesne değiştirmez "salt okunur" bir işlevi olduğunu belirtir. Sabit üye işlevi herhangi bir statik olmayan veri üyesi değiştiremez veya herhangi bir üyenin sabit olmayan işlevlerini çağırın. Sabit üye işlevi bildirmek için yerleştirin **const** bağımsız değişken listesinin kapanış parantezi sonra anahtar sözcük. **Const** anahtar sözcüğü, hem bildirim hem de tanımı gereklidir.  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## <a name="c-and-c-const-differences"></a>C ve C++ const farklılıkları  
 Bir değişken olarak bildirme zaman **const** C kaynak kod dosyasında olarak bunu:  
  
```  
const int i = 2;  
```  
  
 Ardından bu değişken başka bir modül aşağıdaki gibi kullanabilirsiniz:  
  
```  
extern const int i;  
```  
  
 Ancak C++'da aynı davranışı elde etmek üzere bildirmelisiniz, **const** değişken olarak:  
  
```  
extern const int i = 2;  
```  
  
 Bildirmek isterseniz, bir `extern` C kaynak kodu dosyası, kullanım kullanmak için C++ kaynak kodu dosyasına değişken:  
  
```  
extern "C" const int x=10;  
```  
  
 C++ derleyicisi tarafından ad bozma önlemek için.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevin parametre listesi, aşağıdaki durumlarda **const** anahtar sözcüğü belirtir işlevi için bunu çağrılır nesneyi değiştirmez.  
  
 Daha fazla bilgi için **const**, aşağıdaki konulara bakın:  
    
-   [const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)  
  
-   [Tür niteleyicileri (C Dil Başvurusu)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)