---
title: /Zc:noexceptTypes (C++17 noexcept kuralları)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 35bea7c2c629c615c60a6136f289b6b11926c054
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624861"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C++17 noexcept kuralları)

C++ 17 standardı, `noexcept`bir diğer ad `throw()`, `throw(<type list>)` ve `throw(...)`kaldırır ve belirli türlerin `noexcept`içermesini sağlar. Bu değişiklik, C++ 14 veya daha önceki bir sürümü ile uyumlu koddaki kaynak uyumluluk sorunlarına neden olabilir. **/Zc: noexceptTypes** seçeneği, c++ 17 standardına uygunluğu belirler. **/Zc: noexceptTypes-** Code c++ 17 modunda derlendiğinde c++ 14 ve önceki bir davranışına izin verir.

## <a name="syntax"></a>Sözdizimi

> **/Zc: noexceptTypes**[-]

## <a name="remarks"></a>Açıklamalar

**/Zc: noexceptTypes** seçeneği belirtildiğinde, derleyici c++ 17 standardına uyar ve [throw ()](../../cpp/exception-specifications-throw-cpp.md) öğesini [noexcept](../../cpp/noexcept-cpp.md)için bir diğer ad olarak değerlendirir, `throw(<type list>)` ve `throw(...)`kaldırır ve belirli türlerin `noexcept`içermesini sağlar. **/Zc: noexceptTypes** seçeneği yalnızca [/std: c++ 17](std-specify-language-standard-version.md) veya [/std: latest](std-specify-language-standard-version.md) etkin olduğunda kullanılabilir. **/Zc: noexceptTypes** varsayılan olarak ISO c++ 17 standardına uyacak şekilde etkindir. [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: noexceptTypes**'ı etkilemez. **/Std: c++ 17** veya **/std: latest** belirtildiğinde, `noexcept` c++ 14 davranışına dönmek Için **/Zc: noexcepttypes-** öğesini belirterek bu seçeneği kapatın.

Visual Studio 2017 sürüm 15,5 ' den başlayarak, C++ derleyici c++ 17 modundaki bildirimlerde veya [/Permissive-](permissive-standards-conformance.md) seçeneğini belirttiğinizde daha fazla eşleşmeyen özel durum belirtimini tanılar.

Bu örnek, **/Zc: noexceptTypes** seçeneği ayarlandığında veya devre dışı bırakıldığında özel durum belirleyicisi olan bildirimlerin nasıl davranacağını gösterir. Ayarlandığında, `cl /EHsc /W4 noexceptTypes.cpp`kullanarak derleyen davranışı göstermek için. Devre dışı bırakıldığında davranışı göstermek için `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`kullanarak derleyin.

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

Varsayılan **/Zc: noexceptTypes**ayarı kullanılarak derlendiğinde, örnek listelenen uyarıları oluşturur. Kodunuzu güncelleştirmek için, bunun yerine aşağıdakileri kullanın:

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

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: noexcepttypes** veya **/Zc: noexcepttypes** öğesini içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (uyumluluk)](zc-conformance.md)\
[noexcept](../../cpp/noexcept-cpp.md)\
[Özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)
