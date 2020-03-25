---
title: İşleç Aşırı Yüklemesi
ms.date: 11/04/2016
f1_keywords:
- operator_cpp
- operator
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
ms.openlocfilehash: a16f68088ffffd6c3cf38f5ae3adda5f2d59fb57
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188577"
---
# <a name="operator-overloading"></a>İşleç aşırı yüklemesi

**İşleç** anahtar sözcüğü, bir sınıfın örneklerine uygulandığında hangi *işleç-symbol* anlamına geldiğini belirten bir işlev bildirir. Bu, işleci birden çok anlamı veya "aşırı yükleme" sağlar. Derleyici, işlenenlerinin türlerini inceleyerek bir işlecin farklı anlamları arasında ayrım yapar.

## <a name="syntax"></a>Sözdizimi

> *tür* **işleci** *işleci-symbol* **(** *parametre-liste* **)**

## <a name="remarks"></a>Açıklamalar

Birçok yerleşik işlecin işlevini küresel olarak veya sınıf sınıfı temelinde yeniden tanımlayabilirsiniz. Aşırı yüklenmiş işleçler işlev olarak uygulanır.

Aşırı yüklenmiş bir işlecin adı **operator** *x*, burada *x* , aşağıdaki tabloda göründüğü gibi işleçtir. Örneğin, toplama işlecini aşırı yüklemek için **işleç +** adlı bir işlev tanımlarsınız. Benzer şekilde, toplama/atama işlecini aşırı yüklemek için **+=** , **+ =** adlı bir işlev tanımlayın.

### <a name="redefinable-operators"></a>Yeniden tanımlanabilir operatörler

|İşleç|Ad|Tür|
|--------------|----------|----------|
|**,**|Virgül|İkili|
|**!**|Mantıksal DEĞIL|Li|
|**!=**|Eşitsizlik|İkili|
|**%**|Modulus|İkili|
|**%=**|Mod ataması|İkili|
|**&**|Bit düzeyinde AND|İkili|
|**&**|Şunun adresi:|Li|
|**&&**|Mantıksal VE|İkili|
|**&=**|Bit düzeyinde AND ataması|İkili|
|**( )**|İşlev çağrısı|—|
|**( )**|Cast Işleci|Li|
|**&#42;**|Çarpma|İkili|
|**&#42;**|İşaretçi başvurusu|Li|
|**&#42;=**|Çarpma ataması|İkili|
|**+**|Toplama|İkili|
|**+**|Birli artı|Li|
|**++**|Artış <sup>1</sup>|Li|
|**+=**|Toplama ataması|İkili|
|**-**|Çıkarma|İkili|
|**-**|Tekli olumsuzlama|Li|
|**--**|Azaltma <sup>1</sup>|Li|
|**-=**|Çıkarma ataması|İkili|
|**->**|Üye seçimi|İkili|
|**->&#42;**|Üye işaretçisi seçimi|İkili|
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
|**^**|Dışlamalı veya|İkili|
|**^=**|Dışlamalı veya atama|İkili|
|**&#124;**|Bit düzeyinde kapsamalı OR|İkili|
|**&#124;=**|Bit düzeyinde kapsamalı OR ataması|İkili|
|**&#124;&#124;**|Mantıksal VEYA|İkili|
|**~**|Birinin tamamlayıcısı|Li|
|**sil**|Sil|—|
|**new**|Yeni|—|
|dönüştürme işleçleri|dönüştürme işleçleri|Li|

<sup>1</sup> birli artırma ve azaltma işleçlerinin iki sürümü var: preıncrement ve postıncrement.

Daha fazla bilgi için bkz. [operatör aşırı yüklemesi Için genel kurallar](../cpp/general-rules-for-operator-overloading.md) . Aşırı yüklenmiş işleçlerin çeşitli kategorilerindeki kısıtlamalar aşağıdaki konularda açıklanmıştır:

- [Birli Işleçler](../cpp/overloading-unary-operators.md)

- [İkili İşleçler](../cpp/binary-operators.md)

- [Atama](../cpp/assignment.md)

- [İşlev Çağrısı](../cpp/function-call-cpp.md)

- [Alt Simge Oluşturma](../cpp/subscripting.md)

- [Sınıf üyesi erişimi](../cpp/member-access.md)

- [Artış ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).

- [Kullanıcı Tanımlı Tür Dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)

Aşağıdaki tabloda gösterilen işleçler aşırı yüklenemez. Tablo önişlemci sembolleri **#** ve **##** içerir.

### <a name="nonredefinable-operators"></a>Yeniden tanımlanabilir Işleçler

|İşleç|Ad|
|-|-|
|**.**|Üye seçimi|
|**.&#42;**|Üye işaretçisi seçimi|
|**::**|Kapsam çözümlemesi|
|**? :**|Koşullu|
|**#**|Önişlemci dizeye Dönüştür|
|**##**|Önişlemci birleştirme|

Aşırı yüklenmiş işleçler genellikle kod içinde karşılaşıldığında derleyici tarafından örtük olarak çağrılabilir, ancak herhangi bir üye veya üye olmayan işlevle aynı şekilde çağrılabilir:

```cpp
Point pt;
pt.operator+( 3 );  // Call addition operator to add 3 to pt.
```

## <a name="example"></a>Örnek

Aşağıdaki örnek iki karmaşık sayı eklemek için **+** işlecini aşırı yükler ve sonucu döndürür.

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

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
