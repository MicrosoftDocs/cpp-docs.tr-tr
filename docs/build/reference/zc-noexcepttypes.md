---
title: '-Zc: noexceptTypes (C ++ 17 noexcept kurallar) | Microsoft Docs'
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:noexceptTypes
dev_langs:
- C++
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af455b9a781295f3e6f446b7dc5c3d253fe2f4c5
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/ZC:noexceptTypes (c ++ 17 noexcept kurallar)

C ++ 17 standart hale getirir `throw()` için diğer ad olarak `noexcept`, kaldırır `throw(<type list>)` ve `throw(...)`ve dahil etmek belirli türlerine izin verir `noexcept`. Bu kaynak uyumluluk sorunlarını bir dizi C ++ 14 veya önceki uyan kodu neden olabilir. **/Zc:noexceptTypes** seçeneği C ++ 17 standart uyumu belirtin veya kod C ++ 17 modunda derlendiğinde C ++ 14 ve daha önceki davranışını izin verebilirsiniz.

## <a name="syntax"></a>Sözdizimi

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>Açıklamalar

Zaman **/Zc:noexceptTypes** seçeneği belirtildiğinde, derleyicinin C ++ 17 için standart uyan ve değerlendirir [throw()](../../cpp/exception-specifications-throw-cpp.md) için diğer ad olarak [noexcept](../../cpp/noexcept-cpp.md), kaldırır`throw(<type list>)`ve `throw(...)`ve dahil etmek belirli türlerine izin verir `noexcept`. **/Zc:noexceptTypes** seçenek, yalnızca kullanılabilir olduğunda [/Std: c ++ 17](std-specify-language-standard-version.md) veya [/std:latest](std-specify-language-standard-version.md) etkinleştirilir. **/ZC:noexceptTypes** C ++ 17 standart ISO için uygun olması için varsayılan olarak etkindir. [/ İzin veren-](permissive-standards-conformance.md) seçeneği etkilemez **/Zc:noexceptTypes**. Bu seçeneği belirterek kapatmak **/Zc:noexceptTypes-** C ++ 14 davranışını için dönmek için `noexcept` zaman **/std::C ++ 17** veya **/std::latest** belirtilir.

Visual Studio 2017 sürüm 15,5 başlayarak, C++ derleyicisi bildirimlerden C ++ 17 modunda daha fazla eşleşmeyen özel durum belirtimleri tanılar veya ne zaman [/ izin veren-](permissive-standards-conformance.md) seçeneği belirtildi.

Bu örnek, bir özel durum belirticisi bildirimlerle ne zaman nasıl davranacağını göstermektedir **/Zc:noexceptTypes** seçeneğini ayarlayın ya da devre dışı. Davranış göstermek için ayarlandığında, derleme kullanarak `cl /EHsc /W4 noexceptTypes.cpp`. Devre dışı davranış göstermek için derleme kullanarak `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

Varsayılan ayar kullanarak derlendiğinde **/Zc:noexceptTypes**, örnek listelenen uyarılar oluşturur. Kodunuzu güncelleştirmek için aşağıdaki'ı yerine kullanın:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:noexceptTypes** veya **/Zc:noexceptTypes-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)  
[noexcept](../../cpp/noexcept-cpp.md)  
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)  
