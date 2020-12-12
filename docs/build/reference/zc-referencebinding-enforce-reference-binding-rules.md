---
description: 'Daha fazla bilgi edinin:/Zc: referenceBinding (başvuru bağlama kurallarını zorla)'
title: /Zc:referenceBinding (Başvuru bağlama kurallarını zorla)
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: 7d094a2ec3ec680c463a7a756e70e02b9c40c07c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269165"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Başvuru bağlama kurallarını zorla)

**/Zc: referenceBinding** seçeneği belirtildiğinde, derleyici const olmayan bir lvalue başvurusunun geçici bağlama yapmasına izin vermez.

## <a name="syntax"></a>Syntax

> **/Zc: referenceBinding**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: referenceBinding** belirtilirse, derleyici c++ 11 standardının 8.5.3 bölümünü izler: Kullanıcı tanımlı bir türü geçici olarak const olmayan bir dizi başvurusuna bağlayan ifadelere izin vermez. Varsayılan olarak veya **/Zc: referenceBinding-** belirtilmişse, derleyici Microsoft uzantısı olarak böyle ifadelere izin verir, ancak 4. düzey bir uyarı verilir. Kod güvenliği, taşınabilirlik ve uyumluluk için **/Zc: referenceBinding**' i kullanmanızı öneririz.

**/Zc: referenceBinding** seçeneği varsayılan olarak kapalıdır. [/Permissive-](permissive-standards-conformance.md) derleyici seçeneği bu seçeneği örtülü olarak ayarlar, ancak **/Zc: referencebinding-** kullanılarak geçersiz kılınabilir.

## <a name="example"></a>Örnek

Bu örnek, Kullanıcı tanımlı bir türün geçici bir şekilde const olmayan bir başvuruya bağlanmasını sağlayan Microsoft uzantısını gösterir.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

int main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: referencebinding** ' i içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
