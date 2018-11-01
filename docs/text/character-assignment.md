---
title: Karakter Atama
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 9099382a212f9f7bd6c071f4e4d9a0c2bc8887de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435380"
---
# <a name="character-assignment"></a>Karakter Atama

Aşağıdaki örnekte göz önünde bulundurun **sırada** döngü 'X' dışındaki tüm karakterlerle başka bir dizeye kopyalama, bir dize tarar:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

Kod bayt kopyalar `sz2` konumuna işaret ettiği `sz1`, ardından artırır `sz1` sonraki baytı almanın. Ancak sonraki karakteri `sz2` atama için bir çift bayt karakter `sz1` yalnızca ilk bayt kopyalar. Karakter güvenli bir şekilde kopyalamak için bir taşınabilir işlevi ve başka artırmak için aşağıdaki kodu kullanan `sz1` ve `sz2` doğru:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
    {
        _mbscpy_s( sz1, 1, sz2 );
        sz1 = _mbsinc( sz1 );
        sz2 = _mbsinc( sz2 );
    }
    else
        sz2 = _mbsinc( sz2 );
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Karakter Karşılaştırma](../text/character-comparison.md)