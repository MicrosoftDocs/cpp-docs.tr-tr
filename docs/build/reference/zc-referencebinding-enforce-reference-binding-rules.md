---
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
ms.openlocfilehash: b7e297d6fd913ddda4d44a42298a361e314af0b5
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518484"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Başvuru bağlama kurallarını zorla)

**/Zc: referenceBinding** seçeneği belirtildiğinde, derleyici const olmayan bir lvalue başvurusunun geçici bağlama yapmasına izin vermez.

## <a name="syntax"></a>Sözdizimi

> **/Zc:referenceBinding**[ **-** ]

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

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: referencebinding** ' i içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
