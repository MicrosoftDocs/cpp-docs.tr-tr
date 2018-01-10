---
title: "İşleç aşırı yüklemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs: C++
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 617236d30f3c4473f6c7785db97789105d6cd565
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operator-overloading"></a>İşleç Aşırı Yüklemesi
`operator` Anahtar sözcüğü bildirir ne belirten bir işlev `operator-symbol` bir sınıfın örneklerini uygulandığında anlamına gelir. Bu durum, birden fazla anlamı işleci verir veya "overloads". Bir işlecinin işlenenleri türlerini inceleniyor tarafından farklı anlamları arasındaki derleyici ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Genel olarak veya bir sınıf tarafından sınıfı temelinde en yerleşik işleçleri işlevi tanımlayabilirsiniz. Aşırı yüklenmiş işleçler işlevler uygulanır.  
  
 Aşırı yüklenmiş bir işleç adı `operator x`, burada `x` aşağıdaki tabloda göründüğü gibi işlecidir. Örneğin, toplama işleci aşırı yüklemeyi adlı bir işlev tanımladığınız `operator+`. Benzer şekilde, toplama/atama işleci aşırı yüklemeyi `+=`, adlı bir işlev tanımlayın `operator+=`.  
  
### <a name="redefinable-operators"></a>Yeniden tanımlanabilir işleçler  
  
|İşleç|Ad|Tür|  
|--------------|----------|----------|  
|`,`|Virgül|İkili|  
|`!`|Mantıksal değil|Birli|  
|`!=`|Eşitsizlik|İkili|  
|`%`|Mod|İkili|  
|`%=`|Mod ataması|İkili|  
|`&`|Bit düzeyinde AND|İkili|  
|`&`|Şunun adresi:|Birli|  
|`&&`|Mantıksal VE|İkili|  
|`&=`|Bit düzeyinde AND ataması|İkili|  
|`( )`|İşlev çağrısı|—|  
|`( )`|Atama işleci|Birli|  
|`*`|Çarpma|İkili|  
|`*`|İşaretçi başvuru kaldırma|Birli|  
|`*=`|Çarpma ataması|İkili|  
|`+`|Toplama|İkili|  
|`+`|Birli artı|Birli|  
|`++`|Artırma <sup>1</sup>|Birli|  
|`+=`|Toplama ataması|İkili|  
|`-`|Çıkarma|İkili|  
|`-`|Tekli olumsuzlama|Birli|  
|`--`|Azaltma <sup>1</sup>|Birli|  
|`-=`|Çıkarma ataması|İkili|  
|`->`|Üye seçimi|İkili|  
|`->*`|İşaretçi-üye seçimi|İkili|  
|`/`|Bölme|İkili|  
|`/=`|Bölme ataması|İkili|  
|`<`|Küçüktür|İkili|  
|`<<`|Sola kaydırma|İkili|  
|`<<=`|Sola kaydırma atama|İkili|  
|`<=`|Küçüktür veya eşittir|İkili|  
|`=`|Atama|İkili|  
|`==`|Eşitlik|İkili|  
|`>`|Büyüktür|İkili|  
|`>=`|Büyüktür veya eşittir|İkili|  
|`>>`|Sağa kaydırma|İkili|  
|`>>=`|Sağa kaydırma ataması|İkili|  
|`[ ]`|Dizi alt simgesi|—|  
|`^`|Dışlayan OR|İkili|  
|`^=`|Dışlayan OR ataması|İkili|  
|`&#124;`|Bit düzeyinde kapsamalı OR|İkili|  
|`&#124;=`|Bit düzeyinde kapsamalı OR ataması|İkili|  
|`&#124;&#124;`|Mantıksal VEYA|İkili|  
|`~`|Birinin tamamlayıcısı|Birli|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|dönüştürme işleçleri|Birli|  
  
 1 birli iki sürümü artırmak ve azaltma işleçleri var: preincrement ve postincrement.  
  
 Bkz: [İşleç aşırı yüklemesi genel kuralları](../cpp/general-rules-for-operator-overloading.md) daha fazla bilgi için. Aşırı yüklenmiş işleçler çeşitli kategorileri kısıtlamalar aşağıdaki konularda açıklanmıştır:  
  
-   [Birli işleçleri](../cpp/overloading-unary-operators.md)  
  
-   [İkili İşleçler](../cpp/binary-operators.md)  
  
-   [Atama](../cpp/assignment.md)  
  
-   [İşlev çağrısı](../cpp/function-call-cpp.md)  
  
-   [Alt Simge Oluşturma](../cpp/subscripting.md)  
  
-   [Sınıf üye erişimi](../cpp/member-access.md)  
  
-   [Artırma ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
-   [Kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)  
  
 Aşağıdaki tabloda gösterilen işleçleri aşırı yüklenemez. Önişlemci sembolleri tabloyu içeren `#` ve `##`.  
  
### <a name="nonredefinable-operators"></a>Nonredefinable işleçleri  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|Üye seçimi|  
|`.*`|İşaretçi-üye seçimi|  
|`::`|Kapsam çözümlemesi|  
|`? :`|Koşullu|  
|`#`|Dize önişlemci Dönüştür|  
|`##`|Önişlemci birleştirme|  
  
 Kodda karşılaştığında aşırı yüklenmiş işleçler genellikle örtük olarak derleyici tarafından denir olmakla birlikte, aynı şekilde herhangi bir üyesi olarak açıkça çağrılabilir veya dahil olmayan işlev çağrılır:  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek aşırı `+` iki karmaşık numaralar ve sonuç döndüren eklemek için işleci.  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
6.8, 11.2  
```  
  
## <a name="in-this-section"></a>Bu bölümde  
  
1.  [İşleç Aşırı Yüklemesi Genel Kuralları](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [Aşırı Yükleme Birli İşleçleri](../cpp/overloading-unary-operators.md)  
  
3.  [İkili İşleçler](../cpp/binary-operators.md)  
  
4.  [Atama](../cpp/assignment.md)  
  
5.  [İşlev çağrısı](../cpp/function-call-cpp.md)  
  
6.  [Alt Simge Oluşturma](../cpp/subscripting.md)  
  
7.  [Üye Erişimi](../cpp/member-access.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)