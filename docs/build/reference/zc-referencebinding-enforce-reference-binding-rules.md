---
title: '/ ZC: referencebinding (başvuru bağlama kurallarını zorla)'
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
ms.openlocfilehash: 9dfe8f5b4713d9567f6e98af6685c552fb51160e
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57822164"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/ ZC: referencebinding (başvuru bağlama kurallarını zorla)

Zaman **/ZC: referencebinding** seçeneği belirtildiğinde, derleyici geçici bir bağlama bir sabit olmayan lvalue başvuru izin vermiyor.

## <a name="syntax"></a>Sözdizimi

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: referencebinding** belirtilirse, derleyici C ++ 11 standart 8.5.3 bölümünü izler ve geçici bir kullanıcı tanımlı tür sabit olmayan lvalue başvuru bağlama ifadeleri izin vermez. Varsayılan olarak veya **/Zc:referenceBinding-** belirtilirse, derleyici bu tür ifadeleri bir Microsoft uzantısı olarak sağlar, ancak düzey 4 uyarısı verilir. Kod güvenliği, taşınabilirlik ve uyumluluğu için kullanmanızı öneririz **/ZC: referencebinding**.

**/ZC: referencebinding** seçeneği varsayılan olarak kapalıdır. [/ Permissive-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:referenceBinding-**.

## <a name="example"></a>Örnek

Bu örnek, sabit olmayan lvalue başvuru bağlı kullanıcı tanımlı bir tür geçici sağlayan Microsoft uzantısı gösterir.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: referencebinding** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
