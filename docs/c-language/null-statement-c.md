---
description: 'Daha fazla bilgi edinin: null bildiri (C)'
title: Boş Deyim (C)
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
ms.openlocfilehash: 362fc9e311d0495e0a3ab51da7a5042574859649
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243295"
---
# <a name="null-statement-c"></a>Boş Deyim (C)

Bir "boş deyimi", yalnızca noktalı virgül içeren bir deyimdir; bir deyimin olabileceği yerlerde görünebilir. Boş bir deyimi yürütüldüğünde, hiçbir şey olmaz. Boş bir deyimi doğru şekilde kodlamanın yolu aşağıda gösterilmiştir:

## <a name="syntax"></a>Syntax

> **;**

## <a name="remarks"></a>Açıklamalar

,, Ve gibi deyimler, **`do`** **`for`** **`if`** **`while`** bir çalıştırılabilir deyimin deyim gövdesi olarak görünmesini gerektirir. Boş deyim, substantive deyim gövdesini gerekmeyen durumlarda sözdizimi koşullarını karşılar.

Diğer C deyimlerinde olduğu gibi, boş bir deyimden önce etiket ekleyebilirsiniz. Deyim olmayan bir öğeyi (örneğin, bileşik bir deyimin kapanış ayracı) etiketlemek için, boş bir deyimi etiketleyebilir ve aynı etkiyi görmek için onu hemen öğeden önce ekleyebilirsiniz.

Bu örnekte boş deyimi gösterilmektedir:

```C
for ( i = 0; i < 10; line[i++] = 0 )
     ;
```

Bu örnekte, deyiminin döngü ifadesi **`for`** `line[i++] = 0` ilk 10 öğesini öğesinin `line` 0 olarak başlatır. Deyim gövdesi boş bir deyimdir çünkü başka bir deyim gerekli değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
