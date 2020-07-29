---
title: /Zc:noexceptTypes (C++17 noexcept kuralları)
ms.date: 06/04/2020
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 09817372e818a05c389a083aac5f04e03b1ab0e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218955"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C++17 noexcept kuralları)

C++ 17 standardı, `throw()` için bir diğer ad yapar **`noexcept`** , `throw(` *`type-list`* `)` ve kaldırır `throw(...)` ve belirli türlerin dahil etmesine izin verir **`noexcept`** . Bu değişiklik, C++ 14 veya daha önceki bir sürümü ile uyumlu koddaki kaynak uyumluluk sorunlarına neden olabilir. **`/Zc:noexceptTypes`** Seçeneği c++ 17 standardına uygunluğu belirler. **`/Zc:noexceptTypes-`** kod C++ 17 modunda derlendiğinde C++ 14 ve önceki bir davranışına izin verir.

## <a name="syntax"></a>Sözdizimi

> **`/Zc:noexceptTypes`**\[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/Zc:noexceptTypes`** Seçenek belirtildiğinde, derleyici c++ 17 standardına uyar ve [**`throw()`**](../../cpp/exception-specifications-throw-cpp.md) için bir diğer ad olarak davranır [**`noexcept`**](../../cpp/noexcept-cpp.md) , ve ' i kaldırır ve `throw(` *`type-list`* `)` `throw(...)` belirli türlerin dahil etmesine izin verir **`noexcept`** . **`/Zc:noexceptTypes`** Seçeneği yalnızca veya etkin olduğunda kullanılabilir [**`/std:c++17`**](std-specify-language-standard-version.md) [**`/std:c++latest`**](std-specify-language-standard-version.md) . **`/Zc:noexceptTypes`** ISO C++ 17 standardına uymak için varsayılan olarak etkindir. [**`/permissive-`**](permissive-standards-conformance.md)Seçeneği etkilenmez **`/Zc:noexceptTypes`** . **`/Zc:noexceptTypes-`** **`noexcept`** **`/std:c++17`** Ya da belirtildiğinde, c++ 14 davranışına dönülmeyi belirterek bu seçeneği devre dışı bırakın **`/std:c++latest`** .

Visual Studio 2017 sürüm 15,5 ' den başlayarak, C++ derleyicisi, C++ 17 modundaki bildirimlerde veya seçeneğini belirttiğinizde daha fazla eşleşmeyen özel durum belirtimini tanılar [**`/permissive-`**](permissive-standards-conformance.md) .

Bu örnek, **`/Zc:noexceptTypes`** seçenek ayarlandığında veya devre dışı bırakıldığında özel durum belirleyicisi olan bildirimlerin nasıl davranacağını gösterir. Ayarlandığında, kullanarak derleyen davranışı göstermek için `cl /EHsc /W4 noexceptTypes.cpp` . Devre dışı bırakıldığında davranışı göstermek için kullanarak derleyin `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp` .

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

Varsayılan ayar kullanılarak derlendiğinde **`/Zc:noexceptTypes`** , örnek listelenen uyarıları oluşturur. Kodunuzu güncelleştirmek için, bunun yerine aşağıdakileri kullanın:

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

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini, veya içerecek şekilde *`/Zc:noexceptTypes`* değiştirin *`/Zc:noexceptTypes-`* ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[**`/Zc`** Uyumsuzlu](zc-conformance.md)\
[noexcept](../../cpp/noexcept-cpp.md)\
[Özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)
