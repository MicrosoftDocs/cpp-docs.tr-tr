---
title: 'Address-of Işleci: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 4c9ae9aedaec202c8798ab454ee5df1a68278a6d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181609"
---
# <a name="address-of-operator-amp"></a>Address-of Işleci: &amp;

## <a name="syntax"></a>Sözdizimi

```
& cast-expression
```

## <a name="remarks"></a>Açıklamalar

Birli adres işleci ( **&** ) işleneninin adresini alır. Address-of işlecinin işleneni, bir işlev göstergesi veya bit alanı olmayan bir nesneyi atayan bir l değeri olabilir.

Address-of işleci yalnızca temel, yapı, sınıf veya dosya kapsamı düzeyinde belirtilen birleşim türlerine sahip değişkenlere veya alt simge dizisi başvurularına uygulanabilir. Bu ifadelerde, Address-of işlecini içermeyen bir sabit ifade, bir ifadeye eklenebilir veya bu ifadeye çıkarılır.

İşlevlere veya l değerlerine uygulandığında, ifadenin sonucu işlenenin türünden türetilmiş bir işaretçi türüdür (r-value). Örneğin, işlenen **char**türünde ise, ifadenin sonucu **char**türünde bir işaretçisidir. **Const** veya **volatile** nesnelerine uygulanan address-of işleci `const type *` veya `volatile type *`olarak değerlendirilir; burada **tür** özgün nesnenin türüdür.

Address-of işleci nitelenmiş bir ada uygulandığında, sonuç *tam adın* bir statik üye belirttiğinden bağımsız olarak değişir. Bu durumda sonuç, üyenin bildiriminde belirtilen türe yönelik bir işaretçidir. Üye statik değilse, sonuç, sınıfın üye *adının* *nitelenmiş sınıf adı*tarafından belirtilen bir işaretçisidir. ( *Tam sınıf adı*hakkında daha fazla bilgi için bkz. [birincil ifadeler](../cpp/primary-expressions.md) .) Aşağıdaki kod parçası, üyenin statik olup olmadığına bağlı olarak sonucun nasıl farklı olduğunu gösterir:

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

Bu örnekte `&PTM::fValue` ifade, `fValue` statik bir üye olduğundan, `float PTM::*` türü yerine `float *` türü verir.

Aşırı yüklenmiş bir işlevin adresi yalnızca işlevin hangi sürümünün başvurulduğundan açık olduğu durumlarda alınabilir. Belirli bir aşırı yüklenmiş işlevin adresini alma hakkında bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md) .

Bir başvuru türüne adres işlecinin uygulanması, işlecin, başvurunun bağlandığı nesneye uygulanmasıyla aynı sonucu verir. Örneğin:

## <a name="example"></a>Örnek

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

## <a name="output"></a>Çıktı

```Output
&d equals &rd
```

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

## <a name="output"></a>Çıktı

```Output
25
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[İşleçlerin Yöneltmesi ve Adresi](../c-language/indirection-and-address-of-operators.md)
