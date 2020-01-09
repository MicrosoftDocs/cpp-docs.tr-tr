---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 6992ec8b151a83b3f9fa920997845c20caf0476d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317753"
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

Bir [. ](dot-else.md)Bundan sonra, özgün koşul yanlış ise deyimleri yürütülür. Koşulların çalışma zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
