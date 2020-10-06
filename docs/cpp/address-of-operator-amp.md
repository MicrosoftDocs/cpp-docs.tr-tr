---
title: 'Address-of Işleci: &amp;'
description: C++ dilindeki adres operatörü.
ms.date: 10/02/2020
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 8ef7ad065281e4de58ddbdebea25950f8eb9dd06
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765282"
---
# <a name="address-of-operator-amp"></a>Address-of Işleci: &amp;

## <a name="syntax"></a>Sözdizimi

> **`&`** *`cast-expression`*

## <a name="remarks"></a>Açıklamalar

Birli adres işleci ( **`&`** ) işleneninin adresini alır. Address-of işlecinin işleneni, bir işlev göstergesi veya bit alanı olmayan bir nesneyi atayan bir l değeri olabilir.

Address-of işleci yalnızca, dosya kapsamı düzeyinde veya alt simge oluşturan dizi başvurularına göre belirtilen temel, yapı, sınıf veya birleşim türü değişkenlerine uygulanabilir. Bu ifadelerde, Address-of işlecini içermeyen bir sabit ifade, bu ifadeye eklenebilir veya adrese çıkarılır.

İşlevlere veya l değerlerine uygulandığında, ifadenin sonucu işlenenin türünden türetilmiş bir işaretçi türüdür (r-value). Örneğin, işlenen türü ise **`char`** , ifadesinin sonucu, işaretçisine tür olur **`char`** . Ya da nesnelerine uygulanan Address-of işleci **`const`** **`volatile`** , veya olarak değerlendirilir, `const type *` `volatile type *` burada `type` özgün nesnenin türüdür.

Aşırı yüklenmiş bir işlevin adresi yalnızca işlevin hangi sürümünün başvurulduğunu açık olduğunda alınabilir. Belirli bir aşırı yüklenmiş işlevin adresini alma hakkında bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md) .

Address-of işleci nitelenmiş bir ada uygulandığında, sonuç *tam adın* bir statik üye belirttiğinden bağımsız olarak değişir. Bu durumda sonuç, üyenin bildiriminde belirtilen türe yönelik bir işaretçidir. Statik olmayan bir üye için sonuç, *tam sınıf adı*tarafından belirtilen sınıfın üye *adının* bir işaretçisidir. *Nitelenmiş sınıf adı*hakkında daha fazla bilgi için bkz. [birincil ifadeler](../cpp/primary-expressions.md).

## <a name="example-address-of-static-member"></a>Örnek: Statik üyenin adresi

Aşağıdaki kod parçası, bir sınıf üyesinin statik olup olmadığına bağlı olarak, adres işlecinin sonucunun nasıl farklılık gösterdiğini göstermektedir:

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

Bu örnekte, ifadesi `&PTM::fValue` `float *` `float PTM::*` bir statik üye olduğu için türü yerine türü verir `fValue` .

## <a name="example-address-of-a-reference-type"></a>Örnek: bir başvuru türünün adresi

Bir başvuru türüne adres işlecinin uygulanması, işlecin, başvurunun bağlandığı nesneye uygulanmasıyla aynı sonucu verir. Örneğin:

```cpp
// expre_Address_Of_Operator2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   double d;        // Define an object of type double.
   double& rd = d;  // Define a reference to the object.

   // Obtain and compare their addresses
   if( &d == &rd )
      cout << "&d equals &rd" << endl;
}
```

```Output
&d equals &rd
```

## <a name="example-function-address-as-parameter"></a>Örnek: parametre olarak Işlev adresi

Aşağıdaki örnek, bir işleve bir işaretçi bağımsız değişkeni geçirmek için Address-of işlecini kullanır:

```cpp
// expre_Address_Of_Operator3.cpp
// compile with: /EHsc
// Demonstrate address-of operator &

#include <iostream>
using namespace std;

// Function argument is pointer to type int
int square( int *n ) {
   return (*n) * (*n);
}

int main() {
   int mynum = 5;
   cout << square( &mynum ) << endl;   // pass address of int
}
```

```Output
25
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ yerleşik Işleçleri, önceliği ve Ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Yöneltme ve adres Işleçleri](../c-language/indirection-and-address-of-operators.md)
