---
title: C Deyimlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
ms.openlocfilehash: bfa6840553055202f26f55e1dc5971bfd047b2de
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857079"
---
# <a name="overview-of-c-statements"></a>C Deyimlerine Genel Bakış

C deyimleri belirteçler, ifadeler ve diğer deyimlerden oluşur. Başka bir deyimin bileşenini oluşturan bir deyim, kapsayan deyiminin "gövdesi" olarak adlandırılır. Aşağıdaki sözdizimi tarafından belirtilen her deyim türü, bu bölümde ele alınmıştır.

## <a name="syntax"></a>Sözdizimi

*Ekstre*: [etiketli ifade](../c-language/goto-and-labeled-statements-c.md)

[bileşik ifade](../c-language/compound-statement-c.md)

[ifade ifadesi](../c-language/expression-statement-c.md)

[seçim-ifade](../c-language/if-statement-c.md)

[yineleme-ekstresi](../c-language/do-while-statement-c.md)

[sıçrama-deyim](../c-language/break-statement-c.md)

[try-except-deyimin](../c-language/try-except-statement-c.md) /* Microsoft 'a özgü \*/

[try-finally-deyimin](../c-language/try-finally-statement-c.md) /\* Microsoft 'a özgü \*/

Deyim gövdesi çoğu zaman bir "bileşik deyim" olur. Bileşik deyim, anahtar sözcükleri içerebilen diğer deyimlerden oluşur. Bileşik ifade, küme ayraçları ( **{}** ) ile sınırlandırılmıştır. Diğer tüm C deyimleri noktalı virgül ( **;** ) ile biter. Noktalı virgül, bir deyim sonlandırıcısıdır.

İfade deyimi, [ifadelerde ve atamalarında](../c-language/expressions-and-assignments.md)tanıtılan aritmetik veya mantıksal işleçleri Içerebilen bir C ifadesi içerir. null deyimi, boş bir deyimdir.

Bir C deyimi, ad ve üst üste iki noktadan oluşan bir tanımlama etiketi ile başlayabilir. Yalnızca `goto` deyimi deyim etiketlerini tanıdığı için deyim etiketleri `goto` ile ele alınır. Daha fazla bilgi için [goto ve etiketli deyimlere](../c-language/goto-and-labeled-statements-c.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
