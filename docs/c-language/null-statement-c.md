---
title: Boş Deyim (C)
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
ms.openlocfilehash: 4fdfa2283e40856ccaffd55daacb697b1344134b
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148458"
---
# <a name="null-statement-c"></a>Boş Deyim (C)

Bir "boş deyimi", yalnızca noktalı virgül içeren bir deyimdir; bir deyimin olabileceği yerlerde görünebilir. Boş bir deyimi yürütüldüğünde, hiçbir şey olmaz. Boş bir deyimi doğru şekilde kodlamanın yolu aşağıda gösterilmiştir:

## <a name="syntax"></a>Sözdizimi

> **;**

## <a name="remarks"></a>Açıklamalar

Gibi deyimler **yapmak**, **için**, **varsa**, ve `while` deyim gövdesi olarak yürütülebilir bir deyimin görünmesini gerektirir. Boş deyim, substantive deyim gövdesini gerekmeyen durumlarda sözdizimi koşullarını karşılar.

Diğer C deyimlerinde olduğu gibi, boş bir deyimden önce etiket ekleyebilirsiniz. Deyim olmayan bir öğeyi (örneğin, bileşik bir deyimin kapanış ayracı) etiketlemek için, boş bir deyimi etiketleyebilir ve aynı etkiyi görmek için onu hemen öğeden önce ekleyebilirsiniz.

Bu örnekte boş deyimi gösterilmektedir:

```C
for ( i = 0; i < 10; line[i++] = 0 )
     ;
```

Bu örnekte, döngü ifadesi **için** deyimi `line[i++] = 0` ilk 10 öğelerini başlatır `line` 0. Deyim gövdesi boş bir deyimdir çünkü başka bir deyim gerekli değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
