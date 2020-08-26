---
title: C Anahtar Sözcükleri
ms.date: 10/09/2018
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
ms.openlocfilehash: 1b49da349a6552022dfd9e8e66e85634f4694645
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838782"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri

"Anahtar sözcükler" C derleyicisi için özel anlamı olan sözcüklerdir. 7 ve 8. çeviri aşamalarında, tanımlayıcının yazımı ve büyük/küçük harf kullanımı C anahtar sözcüğüyle aynı olamaz. (Ön *Işlemci başvurusunda* [Çeviri aşamaları](../preprocessor/phases-of-translation.md) açıklamasına bakın; tanımlayıcılar hakkında bilgi için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).) C dili aşağıdaki anahtar sözcükleri kullanır:

:::row:::
    :::column:::
        **`auto`**\
        **`double`**\
        **`int`**\
        **`struct`**\
        **`break`**\
        **`else`**\
        **`long`**\
        **`switch`**
    :::column-end:::
    :::column:::
        **`case`**\
        **`enum`**\
        **`register`**\
        **`typedef`**\
        **`char`**\
        **`extern`**\
        **`return`**\
        **`union`**
    :::column-end:::
    :::column:::
        **`const`**\
        **`float`**\
        **`short`**\
        **`unsigned`**\
        **`continue`**\
        **`for`**\
        **`signed`**\
        **`void`**
    :::column-end:::
    :::column:::
        **`default`**\
        **`goto`**\
        **`sizeof`**\
        **`volatile`**\
        **`do`**\
        **`if`**\
        **`static`**\
        **`while`**
    :::column-end:::
:::row-end:::

Anahtar sözcükleri yeniden tanımlayamazsınız. Ancak, C [önişlemci yönergelerini](../preprocessor/preprocessor-directives.md)kullanarak derlemeden önce anahtar sözcüklerin yerine kullanılacak metni belirtebilirsiniz.

**Microsoft'a Özgü**

ANSI C standardı, derleyici uygulamaları için başında iki alt çizgi olan tanımlayıcıların ayrılmasını sağlar. Bu nedenle, Microsoft kuralı Microsoft'a özgü anahtar sözcük adlarından önce iki alt çizgi koymaktır. Bu sözcükler tanımlayıcı adı olarak kullanılamaz. Çift alt çizgilerin kullanımı dahil olmak üzere, adlandırma tanımlayıcıları için ANSI kurallarının açıklaması için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).

Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:

:::row:::
    :::column:::
        **`__asm`**<sup>03</sup>\
        **`dllimport`**<sup>iki</sup>\
        **`__int8`**<sup>03</sup>\
        **`naked`**<sup>iki</sup>\
        **`__based`**<sup>1, 3</sup>
    :::column-end:::
    :::column:::
        **`__except`**<sup>03</sup>\
        **`__int16`**<sup>03</sup>\
        **`__stdcall`**<sup>03</sup>\
        **`__cdecl`**<sup>03</sup>\
        **`__fastcall`**
    :::column-end:::
    :::column:::
        **`__int32`**<sup>03</sup>\
        **`thread`**<sup>iki</sup>\
        **`__declspec`**<sup>03</sup>\
        **`__finally`**<sup>03</sup>\
        **`__int64`**<sup>03</sup>
    :::column-end:::
    :::column:::
        **`__try`**<sup>03</sup>\
        **`dllexport`**<sup>iki</sup>\
        **`__inline`**<sup>03</sup>\
        **`__leave`**<sup>03</sup>
    :::column-end:::
:::row-end:::

<sup>1</sup> **`__based`** anahtar sözcüğü 32-bit ve 64 bit hedef derlemeler için sınırlı kullanımları vardır.

<sup>2</sup> , ile kullanıldığında özel tanımlayıcılardır **`__declspec`** ; diğer bağlamlarda kullanımları sınırlı değildir.

<sup>3</sup> önceki sürümlerle uyumluluk için, bu anahtar sözcükler hem iki önde gelen alt çizgi ile hem de Microsoft uzantıları etkinleştirildiğinde tek başına bir alt çizgi ile kullanılabilir.

Microsoft uzantıları varsayılan olarak etkinleştirilmiştir. Programlarınızın tamamen taşınabilir olduğundan emin olmak için, derleme sırasında [/za \( Disable Language Extensions](../build/reference/za-ze-disable-language-extensions.md) seçeneğini belirterek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bunu yaptığınızda, Microsoft 'a özgü bazı anahtar sözcükler devre dışı bırakılır.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcüklerin çoğu çift alt çizgi ile başlar. Dört özel durum, **`dllexport`** , **`dllimport`** **`naked`** ve, **`thread`** yalnızca ile kullanılır **`__declspec`** ve bu nedenle, önde gelen çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)
