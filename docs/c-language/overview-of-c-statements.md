---
title: C deyimlerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3cf80e6237b21101f737f496eb39688ec6ed0a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387183"
---
# <a name="overview-of-c-statements"></a>C Deyimlerine Genel Bakış
C deyimleri belirteçler, ifadeler ve diğer deyimlerden oluşur. Başka bir deyimin bileşenini oluşturan bir deyim, kapsayan deyiminin "gövdesi" olarak adlandırılır. Aşağıdaki sözdizimi tarafından belirtilen her deyim türü, bu bölümde ele alınmıştır.  
  
## <a name="syntax"></a>Sözdizimi  
 *deyimi*:  
 [Etiketli deyim](../c-language/goto-and-labeled-statements-c.md)  
  
 [Bileşik deyim](../c-language/compound-statement-c.md)  
  
 [ifade deyimi](../c-language/expression-statement-c.md)  
  
 [Seçim deyimi](../c-language/if-statement-c.md)  
  
 [Yineleme deyimi](../c-language/do-while-statement-c.md)  
  
 [atlama deyimi](../c-language/break-statement-c.md)  
  
 [try dışında deyimi](../c-language/try-except-statement-c.md)  
  
 / * Microsoft Specific \* / [try-finally-ifadesi](../c-language/try-finally-statement-c.md)  / \* Microsoft Specific \*/  
  
 Deyim gövdesi çoğu zaman bir "bileşik deyim" olur. Bileşik deyim, anahtar sözcükleri içerebilen diğer deyimlerden oluşur. Bileşik deyim kaşlı ayraç ayrılmış (**{}**). Noktalı virgül ile tüm diğer C deyimlerine bitiş (**;**). Noktalı virgül, bir deyim sonlandırıcısıdır.  
  
 İfade deyimi aritmetik içeren bir C ifadesi içeriyor ya da mantıksal işleçler kullanıma sunulan [ifadeler ve atamalar](../c-language/expressions-and-assignments.md). null deyimi, boş bir deyimdir.  
  
 Bir C deyimi, ad ve üst üste iki noktadan oluşan bir tanımlama etiketi ile başlayabilir. Yalnızca `goto` deyimi deyim etiketlerini tanıdığı için deyim etiketleri `goto` ile ele alınır. Bkz: [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimler](../c-language/statements-c.md)