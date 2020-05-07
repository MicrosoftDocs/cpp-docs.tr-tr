---
title: Bileşik Deyim (C)
ms.date: 11/04/2016
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
ms.openlocfilehash: 42d4c1d21c3e98dfc0281a47a35e033852f8de18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312576"
---
# <a name="compound-statement-c"></a>Bileşik Deyim (C)

Bileşik bir ifade ("Block" olarak da bilinir) genellikle başka bir deyimin gövdesi olarak görünür (örneğin, **IF** ifadesi). [Bildirimler ve türler](../c-language/declarations-and-types.md) , bileşik bir deyimin başlangıcında görünebilen bildirimlerin formunu ve anlamını açıklar.

## <a name="syntax"></a>Sözdizimi

*bileşik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*bildirim-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-liste* *bildirimi*

*Ekstre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre-List* *ekstresi*

Bildirimler varsa, bunların herhangi bir deyimden önce gelmesi gerekir. Bir bileşik deyimin başlangıcında belirtilen her tanımlayıcı kapsam, kendi bildirim noktasından bloğunun sonuna kadar uzanır. Bir iç blokta aynı tanımlayıcıya ait bir bildirim mevcut değilse, blok genelinde görünür.

Bir bileşik deyimdeki tanımlayıcılar, daha önce yalnızca bir olabilen `extern` **yazmaç**, **static**veya `extern`, Except işlevleri ile açıkça belirtilmediği sürece **Otomatik** olarak adlandırılır. İşlev bildirimlerinde `extern` belirticisi devre dışı bırakabilirsiniz ve işlev yine de olur `extern`.

Depolama sınıfı `extern`ile Birleşik bir ifadede bir değişken veya işlev bildirilirse, depolama ayrılmamış ve başlatmaya izin verilmez. Bildirim, başka bir yerde tanımlanmış bir dış değişken veya işleve başvurur.

**Auto** veya **register** anahtar sözcüğüyle bir blokta belirtilen değişkenler yeniden ayrılır ve gerekirse bileşik deyimin her girildiği her seferinde başlatılır. Bu değişkenler bileşik deyimden çıkıldıktan sonra tanımlanmamıştır. Bir blok içinde bildirildiği bir değişkenin **static** özniteliği varsa, program yürütme başladığında değişken başlatılır ve değeri program boyunca tutar. **Statik**hakkında bilgi için bkz. [Depolama sınıfları](../c-language/c-storage-classes.md) .

Bu örnekte bileşik bir ifade gösterilmektedir:

```
if ( i > 0 )
{
    line[i] = x;
    x++;
    i--;
}
```

Bu örnekte, `i` 0 ' dan büyükse, bileşik deyimin içindeki tüm deyimler sırasıyla yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
