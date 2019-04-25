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
ms.openlocfilehash: 1b5863a021fd74bb80162d589af7c2a1a5b36f9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232475"
---
# <a name="overview-of-c-statements"></a>C Deyimlerine Genel Bakış

C deyimleri belirteçler, ifadeler ve diğer deyimlerden oluşur. Başka bir deyimin bileşenini oluşturan bir deyim, kapsayan deyiminin "gövdesi" olarak adlandırılır. Aşağıdaki sözdizimi tarafından belirtilen her deyim türü, bu bölümde ele alınmıştır.

## <a name="syntax"></a>Sözdizimi

*deyimi*: [etiketli deyim](../c-language/goto-and-labeled-statements-c.md)

[Bileşik deyim](../c-language/compound-statement-c.md)

[ifade deyimi](../c-language/expression-statement-c.md)

[Seçimi deyimi](../c-language/if-statement-c.md)

[Yineleme deyimi](../c-language/do-while-statement-c.md)

[atlama-deyimi](../c-language/break-statement-c.md)

[deyimi dışında deneyin](../c-language/try-except-statement-c.md)

/ * Microsoft'a Specific \* / [try-finally deyimi](../c-language/try-finally-statement-c.md)  / \* Microsoft Specific \*/

Deyim gövdesi çoğu zaman bir "bileşik deyim" olur. Bileşik deyim, anahtar sözcükleri içerebilen diğer deyimlerden oluşur. Bileşik deyim, küme ayraçları tarafından ayrılmış (**{}**). Diğer tüm C deyimleri noktalı virgül ile Bitiş (**;**). Noktalı virgül, bir deyim sonlandırıcısıdır.

İfade deyimi aritmetik içerebilen bir C ifadesi içerir veya mantıksal işleçleri [ifadeler ve atamalar](../c-language/expressions-and-assignments.md). null deyimi, boş bir deyimdir.

Bir C deyimi, ad ve üst üste iki noktadan oluşan bir tanımlama etiketi ile başlayabilir. Yalnızca `goto` deyimi deyim etiketlerini tanıdığı için deyim etiketleri `goto` ile ele alınır. Bkz: [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
