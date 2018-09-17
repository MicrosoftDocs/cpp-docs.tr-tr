---
title: '-Zc: noexceptTypes (C ++ 17 noexcept kuralları) | Microsoft Docs'
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 78657b293562e82e4691ae54f8ee60d490d78ba7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716683"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/ ZC: noexcepttypes (c ++ 17 noexcept kuralları)

C ++ 17 standardına yapar `throw()` için bir diğer ad olarak `noexcept`, kaldırır `throw(<type list>)` ve `throw(...)`ve dahil etmek bazı türleri tanır `noexcept`. Bu kaynak uyumluluk sorunlarını bir dizi C ++ 14 veya önceki uyan kodu neden olabilir. **/ZC: noexcepttypes** seçeneği C ++ 17 standart uyumluluk belirtin veya kod C ++ 17 modunda derlendiğinde C ++ 14 ve önceki davranışı izin verebilirsiniz.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: noexcepttypes**[-]

## <a name="remarks"></a>Açıklamalar

Zaman **/ZC: noexcepttypes** seçeneği belirtildiğinde, derleyici C ++ 17'ye standart uyan ve değerlendirir [throw()](../../cpp/exception-specifications-throw-cpp.md) için bir diğer ad olarak [noexcept](../../cpp/noexcept-cpp.md), kaldırır`throw(<type list>)`ve `throw(...)`ve dahil etmek bazı türleri tanır `noexcept`. **/ZC: noexcepttypes** seçeneği, yalnızca kullanılabilir olduğunda [/Std: c ++ 17](std-specify-language-standard-version.md) veya [/std:latest](std-specify-language-standard-version.md) etkinleştirilir. **/ ZC: noexcepttypes** ISO C ++ 17 standardına uygun olması için varsayılan olarak etkindir. [/ Permissive-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: noexcepttypes**. Bu seçeneği belirterek kapatmak **/Zc:noexceptTypes-** C ++ 14 davranışı için dönmek için `noexcept` olduğunda **/std::C ++ 17** veya **/std::latest** belirtilir.

Visual Studio 2017 15.5 sürümünden itibaren C++ Derleyici daha fazla eşleşmeyen bir özel durum belirtimleri C ++ 17 modunda bildirimlerinde tanılar veya [/ permissive-](permissive-standards-conformance.md) seçeneği belirtildi.

Bu örnek, bir özel durum tanımlayıcısı bildirimlerle ne zaman nasıl davranacağını gösterir **/ZC: noexcepttypes** seçeneği ayarlanır veya devre dışı. Davranış gösterecek şekilde ayarlandığında, kullanarak derleme `cl /EHsc /W4 noexceptTypes.cpp`. Kullanarak devre dışı bırakıldığında davranışını göstermek için derleme `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

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

Varsayılan ayar kullanılarak derlendiğinde **/ZC: noexcepttypes**, örnek listelenen uyarılar oluşturur. Kodunuzu güncelleştirmek için aşağıdakileri kullanın:

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

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: noexcepttypes** veya **/Zc:noexceptTypes-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)
