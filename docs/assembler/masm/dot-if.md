---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e8213052dce8d84d62f90d4bc2653435c2b31434
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398230"
---
# <a name="if-32-bit-masm"></a>. IF (32-bit masa)

*Condition1* (ÖRNEĞIN, AX > 7) test eden kodu üretir ve bu koşul doğru ise *deyimleri* yürütür. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> **. Eğer** *condition1*\
> *deyimler*\
> ⟦ **. Condition2 Ise ELSEıF**\
> *deyim*⟧ \
> ⟦ **. ELSE**\
> *deyim*⟧ \
> **.ENDIF**

## <a name="remarks"></a>Açıklamalar

Bir [. ](../../assembler/masm/dot-else.md)Bundan sonra, özgün koşul yanlış ise deyimleri yürütülür. Koşulların çalışma zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
