---
title: '/ ZC: rvaluecast (tür dönüştürme kurallarını zorlama) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 626cabbec169d541a63dd65c22a7380718613b79
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706595"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Tür dönüştürme kurallarını zorlama)

Zaman **/ZC: rvaluecast** seçeneği belirtildiğinde, derleyici C ++ 11 standardına uygun olarak bir dönüştürme işleminin sonucu olarak bir rvalue başvuru türünü doğru tanımlar. Bu seçenek belirtilmediğinde derleyici davranışı Visual Studio 2012 olduğu gibi aynıdır.

## <a name="syntax"></a>Sözdizimi

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: rvaluecast** belirtilirse, derleyici C ++ 11 standardının 5.4 bölümünü izler ve yalnızca yayın neden başvuru olmayan türleri ve işlev olmayan türlerin rvalue başvuruları neden ifadeleri cast ifadeleri rvalue türü. Varsayılan olarak veya **/Zc:rvalueCast-** belirtilirse, derleyici uyumsuzdur ve rvalues olarak rvalue başvuruları sonuçlanan tüm cast ifadeleri gibi davranır. Uyumluluk ve cast kullanımında hatalarını ortadan kaldırmak için kullanmanızı öneririz **/ZC: rvaluecast**.

Varsayılan olarak, **/ZC: rvaluecast** kapalı (**/Zc:rvalueCast-**). [/ Permissive-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:rvalueCast-**.

Kullanım **/ZC: rvaluecast** atama ifadesini bağımsız değişken olarak bir rvalue başvuru türü alan bir işlev için geçirirseniz. Varsayılan çalışma biçimi derleyici hatasına [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) zaman derleyici yanlış belirler atama ifadesi türü. Bu örnek, bir derleyici hatası doğru gösterir ne zaman kod **/ZC: rvaluecast** belirtilmemiş:

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

Varsayılan derleyici çalışma biçimi uygun olduğunda C2102 hata bildirmeyebilir. Ne zaman cast bir kimlik tarafından oluşturulan bir rvalue adresi alınmışsa Bu örnekte, derleyici bir hata bildirmez **/ZC: rvaluecast** belirtilmemiş:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: rvaluecast** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
