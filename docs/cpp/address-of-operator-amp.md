---
title: 'Address-of işleci: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: a03a6100c372e059bd9ef2ddde0558da307923dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385030"
---
# <a name="address-of-operator-amp"></a>Address-of işleci: &amp;

## <a name="syntax"></a>Sözdizimi

```
& cast-expression
```

## <a name="remarks"></a>Açıklamalar

Birli adres işleci (**&**), işlenenin adresini alır. Adres işlecinin işleneni, bir işlev göstergesi veya bit alanı olmayan bir nesneyi gösteren bir l-değeri olabilir.

Address-of işleci yalnızca temel, yapı, sınıf, değişkenleri uygulanabilir veya alt simgeli dizi başvurularına dosya kapsamı düzeyinde, bildirilen değişkenlere veya birleşim türleri. Bu ifadelerde adres işlecini içermeyen sabit bir ifade eklenecek veya adres ifadeden çıkarılabilir.

Bir işaretçi türü (r), işlenenin türü uygulandığında işlevler veya l-değeri, ifadenin sonucu elde edilir. Örneğin, işlenenin türü ise **char**, işaretçi türüne ifadenin sonucu olan **char**. Uygulanan address-of işlecini, **const** veya **geçici** nesneleri, değerlendiren `const type *` veya `volatile type *`burada **türü** özgün türü nesne.

Address-of işlecini bir tam adı için uygulandığında, sonuç bağlıdır *tam ad* statik bir üyeye belirtir. Bu durumda, sonuç üye bildiriminde belirtilen türe işaretçisidir. Üye statik değilse, üye işaretçisi sonucudur *adı* tarafından belirtilen sınıf *tam sınıf adının*. (Bkz [birincil ifadeler](../cpp/primary-expressions.md) hakkında daha fazla bilgi için *tam sınıf adının*.) Aşağıdaki kod parçası, nasıl sonucu, üye statik olup bağlı olarak farklılık gösterir:

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

Bu örnekte, ifade `&PTM::fValue` verir türü `float *` tür yerine `float PTM::*` çünkü `fValue` statik bir üyedir.

Yalnızca işlevin hangi sürümünü başvurulan açık olduğunda, aşırı yüklenmiş bir işlevin adresini alınabilir. Bkz: [işlev aşırı yüklemesi](function-overloading.md) belirli bir adresi elde etme hakkında bilgi için aşırı yüklenmiş işlev.

Address-of işleci bir başvuru türü için uygulama işleci, başvuru bağlı olduğu nesneye uygulama aynı sonucu verir. Örneğin:

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

## <a name="output"></a>Çıkış

```Output
&d equals &rd
```

Aşağıdaki örnek, bir işaretçi bağımsız değişkeni bir işleve geçirilecek address-of işlecini kullanır:

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

## <a name="output"></a>Çıkış

```Output
25
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[İşleçlerin Yöneltmesi ve Adresi](../c-language/indirection-and-address-of-operators.md)