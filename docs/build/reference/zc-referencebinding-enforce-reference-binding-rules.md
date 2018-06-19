---
title: /ZC:referenceBinding (başvuru bağlama kuralları zorla) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30038f6ff73eaa2d9536c3685927458a70209864
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378886"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/ZC:referenceBinding (başvuru bağlama kuralları zorla)

Zaman **/Zc:referenceBinding** seçeneği belirtildiğinde, derleyici, geçici bir bağlamak bir sabit olmayan lvalue başvuru izin vermiyor.

## <a name="syntax"></a>Sözdizimi

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/Zc:referenceBinding** belirtilirse, derleyici C ++ 11 standart 8.5.3 bölümünü izler ve geçici bir kullanıcı tanımlı tür const olmayan lvalue başvuru bağlama ifadeleri izin vermez. Varsayılan olarak, veya **/Zc:referenceBinding-** belirtilirse, bu tür ifadeleri bir Microsoft uzantısı olarak derleyici verir, ancak düzey 4 uyarısı verilir. Kod güvenliği, taşınabilirlik ve uyumluluk için kullanmanız önerilir **/Zc:referenceBinding**.

**/Zc:referenceBinding** seçeneği varsayılan olarak kapalıdır. [/ İzin veren-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:referenceBinding-**.

## <a name="example"></a>Örnek

Bu örnek const olmayan lvalue başvuru bağlanması geçici bir kullanıcı tarafından tanımlanan bir tür sağlayan Microsoft uzantısı gösterir.

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

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:referenceBinding** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
