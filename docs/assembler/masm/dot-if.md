---
description: Hakkında daha fazla bilgi edinin:. IF (32-bit masa)
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e6ce9695f90a90665aee1cdaf15167963360fe04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131683"
---
# <a name="if-32-bit-masm"></a>. IF (32-bit masa)

*Condition1* (ÖRNEĞIN, AX > 7) test eden kodu üretir ve bu koşul doğru ise *deyimleri* yürütür. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Syntax

> **.** *Condition1* ise\
> *deyimler*\
> ⟦**. Condition2 Ise ELSEıF** \
> *deyim*⟧ \
> ⟦**. ELSE**\
> *deyim*⟧ \
> **. ENDIF**

## <a name="remarks"></a>Açıklamalar

Bir [. ](dot-else.md) Bundan sonra, özgün koşul yanlış ise deyimleri yürütülür. Koşulların çalışma zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
