---
title: İşleç aşırı yüklemesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs:
- C++
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae4b7cc2211462b097efbefca580b796d573c59
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408574"
---
# <a name="operator-overloading"></a>İşleç aşırı yüklemesi

**İşleci** anahtar sözcüğü ne belirten bir işlev bildirir *operatör sembolünü* bir sınıfın bir örneği için uygulandığında anlamına gelir. Bu durum, birden fazla anlamı işleci verir veya "aşırı". Derleyicinin tür işlenenlerini inceleme tarafından bir işleci farklı anlamları ayırt eder.

## <a name="syntax"></a>Sözdizimi

> *tür* **işleci** *operatör sembolünü* **(** *parametre-listesi* **)**

## <a name="remarks"></a>Açıklamalar

İşlevi en yerleşik işleçler, genel veya sınıf sınıf olarak tanımlayabilirsiniz. Aşırı yüklenmiş işleçler, işlev olarak uygulanır.

Aşırı yüklenmiş bir işleç adı **işleci** *x*burada *x* aşağıdaki tabloda göründüğü gibi işlecidir. Örneğin, toplama işleci aşırı yükleme için çağrılan bir işlev tanımlamanız **operator +**. Benzer şekilde, toplama/atama işlecini aşırı **+=**, çağrılan işlev tanımla **operator +=**.

### <a name="redefinable-operators"></a>Yeniden tanımlanabilir işleçler

|İşleç|Ad|Tür|
|--------------|----------|----------|
|**,**|Virgül|İkili|
|**\!**|Mantıksal değil|Birli|
|**\!=**|Eşitsizlik|İkili|
|**%**|Mod|İkili|
|**%=**|Mod ataması|İkili|
|**&**|Bit düzeyinde AND|İkili|
|**&**|Şunun adresi:|Birli|
|**&&**|Mantıksal VE|İkili|
|**&=**|Bit düzeyinde AND ataması|İkili|
|**( )**|İşlev çağrısı|—|
|**( )**|Atama işleci|Birli|
|**&#42;**|Çarpma|İkili|
|**&#42;**|İşaretçi başvuru kaldırma|Birli|
|**&#42;=**|Çarpma ataması|İkili|
|**+**|Toplama|İkili|
|**+**|Birli artı|Birli|
|**++**|Artırma <sup>1</sup>|Birli|
|**+=**|Toplama ataması|İkili|
|**-**|Çıkarma|İkili|
|**-**|Tekli olumsuzlama|Birli|
|**--**|Azaltma <sup>1</sup>|Birli|
|**-=**|Çıkarma ataması|İkili|
|**->**|Üye seçimi|İkili|
|**->&#42;**|İşaretçi-üye seçimi|İkili|
|**/**|Bölme|İkili|
|**/=**|Bölme ataması|İkili|
|**\<**|Küçüktür|İkili|
|**<<**|Sola kaydırma|İkili|
|**<<=**|Sola kaydırma ataması|İkili|
|**<=**|Küçüktür veya eşittir|İkili|
|**=**|Atama|İkili|
|**==**|Eşitlik|İkili|
|**>**|Büyüktür|İkili|
|**>=**|Büyüktür veya eşittir|İkili|
|**>>**|Sağa kaydırma|İkili|
|**>>=**|Sağa kaydırma ataması|İkili|
|**[ ]**|Dizi alt simgesi|—|
|**^**|Dışlamalı OR|İkili|
|**^=**|Dışlamalı OR ataması|İkili|
|**&#124;**|Bit düzeyinde kapsamalı OR|İkili|
|**&#124;=**|Bit düzeyinde kapsamalı OR ataması|İkili|
|**&#124;&#124;**|Mantıksal VEYA|İkili|
|**~**|Birinin tamamlayıcısı|Birli|
|**delete**|Sil|—|
|**new**|Yeni|—|
|dönüştürme işleçleri|dönüştürme işleçleri|Birli|

<sup>1</sup> birli iki sürümünü artırmak ve azaltma işleçleri var: artırma öncesi ve artırma sonrası.

Bkz: [işleci aşırı yüklemesi genel kuralları](../cpp/general-rules-for-operator-overloading.md) daha fazla bilgi için. Aşırı yüklenmiş işleçler çeşitli kategorileri kısıtlamalar aşağıdaki konularda açıklanmıştır:

- [Birli işleçler](../cpp/overloading-unary-operators.md)

- [İkili İşleçler](../cpp/binary-operators.md)

- [Atama](../cpp/assignment.md)

- [İşlev Çağrısı](../cpp/function-call-cpp.md)

- [Alt Simge Oluşturma](../cpp/subscripting.md)

- [Sınıf üyesi erişimi](../cpp/member-access.md)

- [Artırma ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).

- [Kullanıcı Tanımlı Tür Dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)

Aşağıdaki tabloda gösterilen işleçleri aşırı yüklenemez. Tabloyu önişlemci sembolleri içeren **#** ve **##**.

### <a name="nonredefinable-operators"></a>Nonredefinable işleçleri

|İşleç|Ad|
|-|-|
|**.**|Üye seçimi|
|**.&#42;**|İşaretçi-üye seçimi|
|**::**|Kapsam çözümlemesi|
|**? :**|Koşullu|
|**#**|Dize önişlemci Dönüştür|
|**##**|Önişlemci Birleştir|

Kodda karşılaştığında aşırı yüklenmiş işleçler genellikle örtük olarak derleyici tarafından çağrılır ancak herhangi bir üyesi olarak aynı şekilde açıkça çağrılabilir veya değiştiricilere işlev çağrılır:

```cpp
Point pt;
pt.operator+( 3 );  // Call addition operator to add 3 to pt.
```

## <a name="example"></a>Örnek

Aşağıdaki örnek aşırı **+** iki karmaşık sayılar ve sonucu döndürür eklemek için işleci.

```cpp
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

```Output
6.8, 11.2
```

## <a name="in-this-section"></a>Bu bölümde

- [İşleç Aşırı Yüklemesi Genel Kuralları](../cpp/general-rules-for-operator-overloading.md)

- [Aşırı Yükleme Birli İşleçleri](../cpp/overloading-unary-operators.md)

- [İkili İşleçler](../cpp/binary-operators.md)

- [Atama](../cpp/assignment.md)

- [İşlev Çağrısı](../cpp/function-call-cpp.md)

- [Alt Simge Oluşturma](../cpp/subscripting.md)

- [Üye Erişimi](../cpp/member-access.md)

## <a name="see-also"></a>Ayrıca bkz.
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)