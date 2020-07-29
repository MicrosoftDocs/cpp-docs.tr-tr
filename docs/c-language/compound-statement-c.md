---
title: Bileşik Deyim (C)
ms.date: 11/04/2016
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
ms.openlocfilehash: 93f7fd24049c744874fb0ab3bda37eedef3a139a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200588"
---
# <a name="compound-statement-c"></a>Bileşik Deyim (C)

Bileşik bir ifade ("Block" olarak da bilinir) genellikle başka bir deyimin gövdesi olarak görünür (örneğin, ifadesi) **`if`** . [Bildirimler ve türler](../c-language/declarations-and-types.md) , bileşik bir deyimin başlangıcında görünebilen bildirimlerin formunu ve anlamını açıklar.

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

Bir bileşik deyimdeki tanımlayıcılar **`auto`** , açıkça,, veya dışında, ancak **`register`** **`static`** **`extern`** yalnızca olabilir **`extern`** . **`extern`** İşlev bildirimlerinde belirticisi devre dışı bırakabilirsiniz ve işlev yine de olur **`extern`** .

Depolama sınıfı ile Birleşik bir ifadede bir değişken veya işlev bildirilirse, depolama ayrılmamış ve başlatmaya izin verilmez **`extern`** . Bildirim, başka bir yerde tanımlanmış bir dış değişken veya işleve başvurur.

Or anahtar sözcüğüyle bir blokta belirtilen değişkenler **`auto`** **`register`** yeniden ayrılır ve gerekirse bileşik deyimin her girildiği her seferinde başlatılır. Bu değişkenler bileşik deyimden çıkıldıktan sonra tanımlanmamıştır. Bir blok içinde bildirildiği bir değişkenin **`static`** özniteliği varsa, program yürütme başladığında değişken başlatılır ve değeri program boyunca tutar. Hakkında bilgi için bkz. [Depolama sınıfları](../c-language/c-storage-classes.md) **`static`** .

Bu örnekte bileşik bir ifade gösterilmektedir:

```
if ( i > 0 )
{
    line[i] = x;
    x++;
    i--;
}
```

Bu örnekte, 0 ' `i` dan büyükse, bileşik deyimin içindeki tüm deyimler sırasıyla yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
