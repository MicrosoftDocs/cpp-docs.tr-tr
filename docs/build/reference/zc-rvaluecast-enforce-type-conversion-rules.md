---
title: /ZC:rvalueCast (tür dönüştürme kurallarını) | Microsoft Docs
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
ms.openlocfilehash: d730563d01a3b59d4f2ac6bbadc980ca51112203
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Tür dönüştürme kurallarını zorlama)

Zaman **/Zc:rvalueCast** seçeneği belirtildiğinde, derleyicinin C ++ 11 standart uygun atama işleminin sonucu olarak bir rvalue başvuru türü doğru şekilde tanımlar. Seçeneği belirtilmedi derleyici davranışı Visual Studio 2012 ile aynı olur.

## <a name="syntax"></a>Sözdizimi

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/Zc:rvalueCast** belirtilirse, C ++ 11 standart 5.4 bölümünü derleyici izler ve davranır yalnızca cast cast işlev olmayan türleri rvalue başvuru sonucu ifadeleri ve neden başvuru olmayan türlerinde ifadeleri rvalue türleri olarak. Varsayılan olarak, veya **/Zc:rvalueCast-** belirtilirse, derleyici uyumlu olmayan olduğu ve rvalues olarak rvalue başvuru sonucu tüm cast ifadeleri değerlendirir. Uyumluluk ve atamalar kullanımını hataları ortadan kaldırmak için kullanmanız önerilir **/Zc:rvalueCast**.

Varsayılan olarak, **/Zc:rvalueCast** kapalı (**/Zc:rvalueCast-**). [/ İzin veren-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:rvalueCast-**.

Kullanım **/Zc:rvalueCast** rvalue başvuru türü götüren bir işleve bağımsız değişken olarak bir cast ifadesi geçirirseniz. Derleyici Hatası varsayılan davranışa neden [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) zaman derleyici yanlış belirler cast ifadesi türü. Bu örnek bir derleyici hatası doğru gösterir ne zaman kod **/Zc:rvalueCast** belirtilmedi:

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

Varsayılan derleyici davranışı hata C2102 uygun olduğunda rapor. Cast bir kimliği tarafından oluşturulan bir rvalue adresini ne zaman alınmışsa Bu örnekte, derleyici hata bildirmez **/Zc:rvalueCast** belirtilmedi:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue 
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:rvalueCast** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
