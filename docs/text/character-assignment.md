---
description: 'Daha fazla bilgi edinin: karakter atama'
title: Karakter Atama
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: d0db79acb8732404016f4a20579aff78ff996c17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187552"
---
# <a name="character-assignment"></a>Karakter Atama

**`while`** Döngünün bir dizeyi taraydığı, ' X ' dışındaki tüm karakterleri başka bir dizeye kopyalarken aşağıdaki örneği göz önünde bulundurun:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

Kod, bayt değerini `sz2` tarafından işaret edilen konuma kopyalar `sz1` ve ardından `sz1` sonraki baytı alacak şekilde artar. Ancak içindeki bir sonraki karakter `sz2` çift baytlık bir karakter ise, atama `sz1` yalnızca ilk baytı kopyalar. Aşağıdaki kod, bir taşınabilir işlevi kullanarak karakteri güvenli bir şekilde ve `sz1` daha sonra artan ve doğru bir şekilde kopyalayabilir `sz2` :

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

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)<br/>
[Karakter karşılaştırması](../text/character-comparison.md)
