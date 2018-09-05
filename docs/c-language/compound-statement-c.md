---
title: Statement (C) bileşik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e13f09defccb0aeb3d4ec47cf7cf1678deaee6dd
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767809"
---
# <a name="compound-statement-c"></a>Bileşik Deyim (C)

Bileşik deyim (Ayrıca adlı bir "yapı taşıdır") genellikle başka bir deyim gövdesi olarak aşağıdaki gibi görünür **varsa** deyimi. [Bildirimler ve türler](../c-language/declarations-and-types.md) bileşik bir deyimin kafası görünebilir bildirimleri anlamını ve formu tanımlar.

## <a name="syntax"></a>Sözdizimi

*Bileşik deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *bildirim listesi*<sub>iyileştirilmiş</sub> *deyim listesindeki*<sub>iyileştirilmiş</sub> **}**

*bildirim listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim listesi* *bildirimi*

*ifade listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin* *deyimi*

Bildirimleri varsa, bunlar önce herhangi bir deyim gelmelidir. Bileşik deyim başında bildirilen her bir tanımlayıcının kapsamını, bildirim noktasından bloğun sonuna kadar genişletir. Tanımlayıcısının bildirimi iç bloğu içinde olmadığı sürece blok içinde görülebilir.

Bileşik deyim tanımlayıcıları varsayılmıştır **otomatik** açıkça aksi ile bildirilen sürece **kaydetme**, **statik**, veya `extern`, İşlevler, hariç yalnızca olabilen `extern`. Devre dışı bırakabilirsiniz `extern` işlev bildirimleri ve işlev Belirleyicisi hala olacaktır `extern`.

Depolama ayrılmamış bir değişken, başlatma izin verilmez ve depolama sınıfı ile bileşik deyim içinde bildirilen işlev `extern`. Bildirimi bir dış değişkenine başvuruyor veya işlev başka bir yerde tanımlanmış.

İle bir blok içinde tanımlanan değişkenleri **otomatik** veya **kaydetme** anahtar sözcüğü yeniden ve gerekirse başlatıldı, her zaman bileşik deyim girilir. Bileşik deyim çıkıldı sonra bu değişkenleri tanımlı değil. Bir blok içinde bildirilen bir değişken sahipse **statik** öznitelik, değişken, programın yürütülmesi başlar ve değerini program boyunca tutar başlatılır. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) hakkında bilgi için **statik**.

Bu örnekte, bir bileşik deyimi gösterilmektedir:

```
if ( i > 0 )
{
    line[i] = x;
    x++;
    i--;
}
```

Bu örnekte, `i` 0'dan büyük olan tüm ifadeleri bileşik deyim içinde sırayla yürütülür.

## <a name="see-also"></a>Ayrıca Bkz.
[Deyimler](../c-language/statements-c.md)