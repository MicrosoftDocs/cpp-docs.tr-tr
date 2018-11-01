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
ms.openlocfilehash: baf2106f015a4e8557cb8469d300709694e06d84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428333"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: referencebinding** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
