---
title: /Zc:referenceBinding (Enforce reference binding rules) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8e3b10f5b2108a4c0e29d802951015749775a27
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Enforce reference binding rules)

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
