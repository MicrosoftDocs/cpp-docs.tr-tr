---
description: Daha fazla bilgi için bkz. arabellek taşması
title: Arabellek Taşması
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 17da102b9a48a34d9879c08f0470ced3852ed0ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187604"
---
# <a name="buffer-overflow"></a>Arabellek Taşması

Karakterleri bir arabelleğe yerleştirdiğinizde, değişen karakter boyutları sorunlara neden olabilir. Dizeyi bir dizeden, arabelleğe bir dizeye kopyalayan aşağıdaki kodu göz önünde bulundurun `sz` `rgch` :

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

Soru: son bayt bir ön bayt kopyaladınız mı? Arabelleği taşabileceğinden, aşağıdakiler sorunu çözmez:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy`Çağrı doğru bir şeyi yapmayı dener — 1 veya 2 bayt olsun, tam karakteri kopyalayın. Ancak, karakter 2 baytlık genişse, kopyaladığınız son karakterin arabelleğe sığmadığını hesaba almaz. Doğru çözüm şunlardır:

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Bu kod, `_mbclen` tarafından işaret edilen geçerli karakterin boyutunu test etmek için kullanarak döngü testinde olası arabellek taşması için test eder `sz` . İşleve bir çağrı yaparak `_mbsnbcpy` , **`while`** döngüdeki kodu tek bir kod satırıyla değiştirebilirsiniz. Örneğin:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)
