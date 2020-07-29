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
ms.openlocfilehash: 822bd5efb3125e69ff60aa42ba6419969cace403
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227237"
---
# <a name="operator-overloading"></a>İşleç aşırı yüklemesi

**`operator`** Anahtar sözcüğü, bir sınıfın örneklerine uygulandığında *işleç sembolünün* ne anlama geldiğini belirten bir işlev bildirir. Bu, işleci birden çok anlamı veya "aşırı yükleme" sağlar. Derleyici, işlenenlerinin türlerini inceleyerek bir işlecin farklı anlamları arasında ayrım yapar.

## <a name="syntax"></a>Sözdizimi

> *tür* **`operator`** *operator-symbol* **(** *parametre-listesi* **)**

## <a name="remarks"></a>Açıklamalar

Birçok yerleşik işlecin işlevini küresel olarak veya sınıf sınıfı temelinde yeniden tanımlayabilirsiniz. Aşırı yüklenmiş işleçler işlev olarak uygulanır.

Daha aşırı yüklenmiş bir işlecin adı **`operator`** *x*olur, burada *x* , aşağıdaki tabloda göründüğü gibi işleçtir. Örneğin, toplama işlecini aşırı yüklemek için **işleç +** adlı bir işlev tanımlarsınız. Benzer şekilde, toplama/atama işlecinin yükünü aşırı yüklemek için **+=** , **işleç + =** adlı bir işlev tanımlayın.

### <a name="redefinable-operators"></a>Yeniden tanımlanabilir operatörler

|İşleç|Ad|Tür|
|--------------|----------|----------|
|**,**|Virgül|İkili|
|**!**|Mantıksal NOT|Birli|
|**!=**|Eşitsizlik|İkili|
|**%**|Mod|İkili|
|**%=**|Mod ataması|İkili|
|**&**|Bit düzeyinde AND|İkili|
|**&**|Şunun adresi:|Birli|
|**&&**|Mantıksal VE|İkili|
|**&=**|Bit düzeyinde AND ataması|İkili|
|**( )**|İşlev çağrısı|—|
|**( )**|Cast Işleci|Birli|
|**&#42;**|Çarpma|İkili|
|**&#42;**|İşaretçi başvurusu|Birli|
|**&#42;=**|Çarpma ataması|İkili|
|**+**|Toplama|İkili|
|**+**|Birli artı|Birli|
|**++**|Artış <sup>1</sup>|Birli|
|**+=**|Toplama ataması|İkili|
|**-**|Çıkarma|İkili|
|**-**|Tekli olumsuzlama|Birli|
|**--**|Azaltma <sup>1</sup>|Birli|
|**-=**|Çıkarma ataması|İkili|
|**->**|Üye seçimi|İkili|
|**->&#42;**|Üye işaretçisi seçimi|İkili|
|**/**|Bölüm|İkili|
|**/=**|Bölme ataması|İkili|
|**\<**|Küçüktür|İkili|
|**<<**|Sola kaydırma|İkili|
|**<<=**|Sola kaydırma ataması|İkili|
|**<=**|Küçük veya eşittir|İkili|
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
|**&#124;&#124;**|Mantıksal EĞER|İkili|
|**~**|Birinin tamamlayıcısı|Birli|
|**`delete`**|Sil|—|
|**`new`**|Yeni|—|
|dönüştürme işleçleri|dönüştürme işleçleri|Birli|

<sup>1</sup> birli artırma ve azaltma işleçlerinin iki sürümü var: preıncrement ve postıncrement.

Daha fazla bilgi için bkz. [operatör aşırı yüklemesi Için genel kurallar](../cpp/general-rules-for-operator-overloading.md) . Aşırı yüklenmiş işleçlerin çeşitli kategorilerindeki kısıtlamalar aşağıdaki konularda açıklanmıştır:

- [Birli Işleçler](../cpp/overloading-unary-operators.md)

- [İkili Işleçler](../cpp/binary-operators.md)

- [Atama](../cpp/assignment.md)

- [İşlev çağrısı](../cpp/function-call-cpp.md)

- [Alt Simge Oluşturma](../cpp/subscripting.md)

- [Sınıf üyesi erişimi](../cpp/member-access.md)

- [Artış ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).

- [Kullanıcı tanımlı tür dönüştürmeleri](../cpp/user-defined-type-conversions-cpp.md)

Aşağıdaki tabloda gösterilen işleçler aşırı yüklenemez. Tablo önişlemci sembolleri **#** ve içerir **##** .

### <a name="nonredefinable-operators"></a>Yeniden tanımlanabilir Işleçler

|İşleç|Ad|
|-|-|
|**.**|Üye seçimi|
|**. &#42;**|Üye işaretçisi seçimi|
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

Aşağıdaki örnek **+** iki karmaşık sayı eklemek için işlecini aşırı yükler ve sonucu döndürür.

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

- [Işleç aşırı yüklemesi için genel kurallar](../cpp/general-rules-for-operator-overloading.md)

- [Birli Işleçleri aşırı yükleme](../cpp/overloading-unary-operators.md)

- [İkili Işleçler](../cpp/binary-operators.md)

- [Atama](../cpp/assignment.md)

- [İşlev çağrısı](../cpp/function-call-cpp.md)

- [Alt Simge Oluşturma](../cpp/subscripting.md)

- [Üye erişimi](../cpp/member-access.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
