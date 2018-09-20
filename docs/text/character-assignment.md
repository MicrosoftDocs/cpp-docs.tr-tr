---
title: Karakter atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e17ace90abef63ce4af1dd56b5bbe8dfed9510c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429558"
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