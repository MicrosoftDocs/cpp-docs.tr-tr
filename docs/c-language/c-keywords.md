---
title: C Anahtar Sözcükleri
description: Standart C ve Microsoft C derleyicisi uzantılarında anahtar sözcükler.
ms.date: 12/8/2020
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.openlocfilehash: 1bcef118881a0596406d6ff455dd453220ff81c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300391"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri

*Anahtar sözcükler* C derleyicisi için özel anlamı olan sözcüklerdir. Çeviri aşamaları 7 ve 8 ' de bir tanımlayıcı, C anahtar sözcüğüyle aynı yazım ve büyük/küçük harfe sahip olamaz. Daha fazla bilgi için bkz. *Önişlemci başvurusundaki* [Çeviri aşamaları](../preprocessor/phases-of-translation.md) . Tanımlayıcılar hakkında daha fazla bilgi için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).

## <a name="standard-c-keywords"></a>Standart C anahtar sözcükleri

C dili aşağıdaki anahtar sözcükleri kullanır:

:::row:::
    :::column:::
        **`auto`**\
        **`break`**\
        **`case`**\
        **`char`**\
        **`const`**\
        **`continue`**\
        **`default`**\
        **`do`**\
        **`double`**\
        **`else`**\
        **`enum`**
    :::column-end:::
    :::column:::
        **`extern`**\
        **`float`**\
        **`for`**\
        **`goto`**\
        **`if`**\
        **`inline`**<sup>1, a</sup>\
        **`int`**\
        **`long`**\
        **`register`**\
        **`restrict`**<sup>1, a</sup>\
        **`return`**
    :::column-end:::
    :::column:::
        **`short`**\
        **`signed`**\
        **`sizeof`**\
        **`static`**\
        **`struct`**\
        **`switch`**\
        **`typedef`**\
        **`union`**\
        **`unsigned`**\
        **`void`**\
        **`volatile`**
    :::column-end:::
    :::column:::
        **`while`**\
        **`_Alignas`**<sup>2, a</sup>\
        **`_Alignof`**<sup>2, a</sup>\
        **`_Atomic`**<sup>2, b</sup>\
        **`_Bool`**<sup>1, a</sup>\
        **`_Complex`**<sup>1, b</sup>\
        **[`_Generic`](generic_selection.md)**<sup>2, a</sup>\
        **`_Imaginary`**<sup>1, b</sup>\
        **`_Noreturn`**<sup>2, a</sup>\
        **`_Static_assert`**<sup>2, a</sup>\
        **`_Thread_local`**<sup>2, b</sup>
    :::column-end:::
:::row-end:::

<sup>1</sup>  ISO C99 içinde tanıtılan anahtar sözcükler.

<sup>2</sup>   ISO C11 içinde tanıtılan anahtar sözcükler.

Visual Studio 2019 sürüm 16,8 ' <sup>den başlayarak bu</sup> anahtar sözcükler, **`/std:c11`** veya derleyici seçenekleri belirtildiğinde C olarak derlenen kodda desteklenir **`/std:c17`** .

<sup>b</sup>  Visual Studio 2019 sürüm 16,8 ' den başlayarak, bu anahtar sözcükler tanınıyorsa, **`/std:c11`** veya **`/std:c17`** derleyici seçenekleri belirtildiğinde C olarak derlenen kodda derleyici tarafından desteklenmez.

Anahtar sözcükleri yeniden tanımlayamazsınız. Ancak, C [önişlemci yönergelerini](../preprocessor/preprocessor-directives.md)kullanarak derlemeden önce anahtar sözcüklerin yerine geçecek metni belirtebilirsiniz.

## <a name="microsoft-specific-c-keywords"></a>Microsoft 'a özgü C anahtar sözcükleri

ANSI ve ISO C standartları, iki önde gelen alt çizgi içeren tanımlayıcılara derleyici uygulamaları için ayrılmış olarak izin verir. Microsoft kuralı, Microsoft 'a özgü anahtar sözcük adlarından önce iki alt çizgi ile önce gelmelidir. Bu sözcükler tanımlayıcı adı olarak kullanılamaz. Çift alt çizgilerin kullanımı dahil olmak üzere adlandırma tanımlayıcıları için kuralların açıklaması için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).

Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:

:::row:::
    :::column:::
        **`__asm`**<sup>e</sup>\
        **`__based`**<sup>3, 5</sup>\
        **`__cdecl`**<sup>e</sup>\
        **`__declspec`**<sup>e</sup>\
        **`__except`**<sup>e</sup>\
        **`__fastcall`**\
        **`__finally`**<sup>e</sup>
    :::column-end:::
    :::column:::
        **`__inline`**<sup>e</sup>\
        **`__int16`**<sup>e</sup>\
        **`__int32`**<sup>e</sup>\
        **`__int64`**<sup>e</sup>\
        **`__int8`**<sup>e</sup>\
        **`__leave`**<sup>e</sup>\
        **`__restrict`**
    :::column-end:::
    :::column:::
        **`__stdcall`**<sup>e</sup>\
        **`__try`**<sup>e</sup>\
        **`dllexport`**<sup>4</sup>\
        **`dllimport`**<sup>4</sup>\
        **`naked`**<sup>4</sup>\
        **`static_assert`**<sup>inç</sup>\
        **`thread`**<sup>4</sup>
    :::column-end:::
:::row-end:::

<sup>3</sup> **`__based`** anahtar sözcüğü 32-bit ve 64 bit hedef derlemeler için sınırlı kullanımları vardır.

<sup>4</sup> bunlar ile kullanıldığında özel tanımlayıcılardır **`__declspec`** ; diğer bağlamlarda kullanımları Kısıtlanmamış olur.

<sup>5</sup> önceki sürümlerle uyumluluk için, bu anahtar sözcükler hem iki önde gelen alt çizgi ile hem de Microsoft uzantıları etkinleştirildiğinde tek başına bir alt çizgi ile kullanılabilir.

<sup>6</sup> <onayı. h> eklemezseniz, Microsoft Visual C derleyicisi **`static_assert`** C11 **`_Static_assert`** anahtar sözcüğüne eşlenir.

Microsoft uzantıları varsayılan olarak etkinleştirilmiştir. Taşınabilir kod oluşturmaya yardımcı olmak için, derleme sırasında [/za \( Disable Language Extensions](../build/reference/za-ze-disable-language-extensions.md) seçeneğini belirterek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bu seçeneği kullandığınızda, Microsoft 'a özgü bazı anahtar sözcükler devre dışı bırakılır.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. Standartlar uyumluluğu için, bu anahtar sözcüklerin çoğu bir çift alt çizgi ile önceden başlar. Dört özel durum, **`dllexport`** , **`dllimport`** **`naked`** ve, **`thread`** yalnızca ile kullanılır **`__declspec`** ve önünde çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)
