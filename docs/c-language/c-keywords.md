---
title: C Anahtar Sözcükleri
ms.date: 10/09/2018
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
ms.openlocfilehash: 92704572c40812141911e151faf1a8d331a1ed38
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520441"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri

"Anahtar sözcükler" C derleyicisi için özel anlamı olan sözcüklerdir. 7 ve 8. çeviri aşamalarında, tanımlayıcının yazımı ve büyük/küçük harf kullanımı C anahtar sözcüğüyle aynı olamaz. (Ön *Işlemci başvurusunda* [Çeviri aşamaları](../preprocessor/phases-of-translation.md) açıklamasına bakın; tanımlayıcılar hakkında bilgi için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).) C dili aşağıdaki anahtar sözcükleri kullanır:

:::row:::
    :::column:::
        **`auto`**<br/>
        **`double`**<br/>
        **`int`**<br/>
        **`struct`**<br/>
        **`break`**<br/>
        **`else`**<br/>
        **`long`**<br/>
        **`switch`**<br/>
    :::column-end:::
    :::column:::
        **`case`**<br/>
        **`enum`**<br/>
        **`register`**<br/>
        **`typedef`**<br/>
        **`char`**<br/>
        **`extern`**<br/>
        **`return`**<br/>
        **`union`**<br/>
    :::column-end:::
    :::column:::
        **`const`**<br/>
        **`float`**<br/>
        **`short`**<br/>
        **`unsigned`**<br/>
        **`continue`**<br/>
        **`for`**<br/>
        **`signed`**<br/>
        **`void`**<br/>
    :::column-end:::
    :::column:::
        **`default`**<br/>
        **`goto`**<br/>
        **`sizeof`**<br/>
        **`volatile`**<br/>
        **`do`**<br/>
        **`if`**<br/>
        **`static`**<br/>
        **`while`**<br/>
    :::column-end:::
:::row-end:::

Anahtar sözcükleri yeniden tanımlayamazsınız. Ancak, C [önişlemci yönergelerini](../preprocessor/preprocessor-directives.md)kullanarak derlemeden önce anahtar sözcüklerin yerine kullanılacak metni belirtebilirsiniz.

**Microsoft'a Özgü**

ANSI C standardı, derleyici uygulamaları için başında iki alt çizgi olan tanımlayıcıların ayrılmasını sağlar. Bu nedenle, Microsoft kuralı Microsoft'a özgü anahtar sözcük adlarından önce iki alt çizgi koymaktır. Bu sözcükler tanımlayıcı adı olarak kullanılamaz. Çift alt çizgilerin kullanımı dahil olmak üzere, adlandırma tanımlayıcıları için ANSI kurallarının açıklaması için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).

Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:

:::row:::
    :::column:::
        **`__asm`**<sup>03</sup><br/>
        **`dllimport`**<sup>iki</sup><br/>
        **`__int8`**<sup>03</sup><br/>
        **`naked`**<sup>iki</sup><br/>
        **`__based`**<sup>1, 3</sup><br/>
    :::column-end:::
    :::column:::
        **`__except`**<sup>03</sup><br/>
        **`__int16`**<sup>03</sup><br/>
        **`__stdcall`**<sup>03</sup><br/>
        **`__cdecl`**<sup>03</sup><br/>
        **`__fastcall`**<br/>
    :::column-end:::
    :::column:::
        **`__int32`**<sup>03</sup><br/>
        **`thread`**<sup>iki</sup><br/>
        **`__declspec`**<sup>03</sup><br/>
        **`__finally`**<sup>03</sup><br/>
        **`__int64`**<sup>03</sup><br/>
    :::column-end:::
    :::column:::
        **`__try`**<sup>03</sup><br/>
        **`dllexport`**<sup>iki</sup><br/>
        **`__inline`**<sup>03</sup><br/>
        **`__leave`**<sup>03</sup><br/>
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
