---
description: 'Daha fazla bilgi edinin:/Zc: rvalueCast (tür dönüştürme kurallarını zorla)'
title: /Zc:rvalueCast (Tür dönüştürme kurallarını zorlama)
ms.date: 02/18/2020
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: f9739f16b12e5e0335f17bb5a56ed1e4aa265e9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269152"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Tür dönüştürme kurallarını zorlama)

**`/Zc:rvalueCast`** Seçenek belirtildiğinde, derleyici bir rvalue başvuru türünü bir atama işleminin sonucu olarak doğru şekilde tanımlar. Davranışı C++ 11 standardına uyar. Seçenek belirtilmediğinde, derleyici davranışı Visual Studio 2012 ile aynıdır.

## <a name="syntax"></a>Syntax

> **`/Zc:rvalueCast`**\
> **`/Zc:rvalueCast-`**

## <a name="remarks"></a>Açıklamalar

**`/Zc:rvalueCast`** Belirtilmişse, derleyici c++ 11 standardına ait 5,4 bölümünü izler ve yalnızca, başvuru olmayan türler ve atama ifadeleri ile işlev olmayan türlere ve rvalue türlerine neden olan atama ifadelerine neden olan cast ifadeleri değerlendirir. Varsayılan olarak, veya **`/Zc:rvalueCast-`** belirtilirse, derleyici uyumlu değildir ve Rvalue başvuruları ile rvalues 'a neden olan tüm atama ifadelerini değerlendirir. Uyumluluk için ve bu tür yayınları kullanarak hataları ortadan kaldırmak için kullanmanızı öneririz **`/Zc:rvalueCast`** .

Varsayılan olarak **`/Zc:rvalueCast`** Kapalı ( **`/Zc:rvalueCast-`** ). [/Permissive-](permissive-standards-conformance.md) derleyici seçeneği bu seçeneği örtülü olarak ayarlar, ancak kullanılarak geçersiz kılınabilir **`/Zc:rvalueCast-`** .

Bir **`/Zc:rvalueCast`** atama ifadesini, bir rvalue başvuru türü alan bir işleve bağımsız değişken olarak geçirirseniz kullanın. Derleyici, atama ifadesinin türünü yanlış belirlediğinde, varsayılan davranış derleyici hatası [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) neden olur. Bu örnekte, belirtilmediğinde doğru kodda bir derleyici hatası gösterilmektedir **`/Zc:rvalueCast`** :

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

Varsayılan derleyici davranışı uygun olduğunda hata C2102 raporlamayabilir. Bu örnekte, bir kimlik yayını tarafından oluşturulan bir rvalue adresi belirtilmemişse derleyici bir hata bildirmez **`/Zc:rvalueCast`** :

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** özellik sayfasını seçin.

1. **Tür dönüştürme kurallarını zorla** özelliğini veya olarak ayarlayın **`/Zc:rvalueCast`** **`/Zc:rvalueCast-`** . Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
