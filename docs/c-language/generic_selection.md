---
title: Genel seçim (C11)
description: Microsoft Visual C derleyicisi 'nda kullanılan C11 _Generic anahtar sözcüğünü açıklar
ms.date: 12/9/2020
helpviewer_keywords:
- _Generic keyword [C]
ms.openlocfilehash: de0e840c19186219d53800b9d008d7695b807bc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97349419"
---
# <a name="generic-selection-c11"></a>Genel seçim (C11)

**`_Generic`** Bağımsız değişkenin türüne göre derleme zamanında bir ifade seçen kodu yazmak için anahtar sözcüğünü kullanın. Bağımsız değişken türünün hangi işlevin çağrılacağını seçmesi dışında, C++ ' da aşırı yüklenmesine benzer.

Örneğin, ifadesi `_Generic(42, int: "integer", char: "character", default: "unknown");` türünü değerlendirir `42` ve listede eşleşen türü arar `int` . Bulur ve döndürür `"integer"` .

## <a name="syntax"></a>Syntax

*`generic-selection`*:\
&nbsp;&nbsp;&nbsp;&nbsp;**`_Generic`** **(** *`assignment-expression`, `assoc-list`* **)**

*`assoc-list`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`association`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`assoc-list`, `association`*

*`association`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`type-name`* : *`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;**`default`** : *`assignment-expression`*

İlki *`assignment-expression`* denetim ifadesi olarak adlandırılır. Denetim ifadesinin türü derleme sırasında belirlenir ve *`assoc-list`* hangi ifadenin değerlendirileceğini ve geri dönebileceğini bulmak için ile eşleştirilir. Denetleme ifadesi değerlendirilmez. Örneğin, `_Generic(intFunc(), int: "integer", default: "error");` çalışma zamanında öğesine çağrı yapmaz `intFunc()` . 

Denetim ifadesinin türü saptandıktan sonra,, `const`  `volatile` ve `restrict` eşleştirmeden önce kaldırılır *`assoc-list`* .

Seçilmemiş olmayan içindeki girişler `assoc-list` değerlendirilmez.

## <a name="constraints"></a>Kısıtlamalar

- *`assoc-list`* Aynı türü birden çok kez belirtemez.
- *`assoc-list`* Bir numaralandırma ve ilgili numaralandırmanın temel alınan türü gibi birbirleriyle uyumlu olan türleri belirtemez.
- Genel seçim varsayılan değer içermiyorsa, denetim ifadesinin genel ilişkilendirme listesinde yalnızca bir uyumlu tür adı olması gerekir.

## <a name="example"></a>Örnek

Kullanmanın bir yolu **`_Generic`** bir makrodur. <tgmath. h> üstbilgi dosyası, bağımsız değişkenin türüne göre doğru matematik işlevini çağırmak için **_Generic** kullanır. Örneğin, için makrosu, bir çağrıyı bir `cos()` `cosf()` , karmaşık çift ile eşleştirirken bir float ile eşler `ccos()` .

Aşağıdaki örnek, kendisine geçirdiğiniz bağımsız değişkenin türünü tanımlayan bir makronun nasıl yazılacağını gösterir. `"unknown"`İçinde denetim ifadesiyle eşleşen hiçbir giriş yoksa üretir *`assoc-list`* :

```C
// Compile with /std:c11

#include <stdio.h>

/* Get a type name string for the argument x */
#define TYPE_NAME(X) _Generic((X), \
      int: "int", \
      char: "char", \
      double: "double", \
      default: "unknown")

int main()
{
    printf("Type name: %s\n", TYPE_NAME(42.42));

    // The following would result in a compile error because 
    // 42.4 is a double, doesn't match anything in the list, 
    // and there is no default.
    // _Generic(42.4, int: "integer", char: "character"));
}

/* Output:
Type name: double
*/

```

## <a name="see-also"></a>Ayrıca bkz.

[`/std` (Dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)\
[Türe özel matematik](../c-runtime-library/tgmath.md)