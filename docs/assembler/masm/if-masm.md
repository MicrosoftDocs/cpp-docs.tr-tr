---
title: IF (MASM)
ms.date: 12/17/2019
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 38d366a3a41e7b08759594899cdcbb2cb84dfbfa
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317298"
---
# <a name="if"></a>IF

*İfade1 true* ise (sıfır dışında) veya *İfade1* yanlış (0) *ise ve* *İfade2* true ise, *ifdeyimlerin* derlemesini verir.

## <a name="syntax"></a>Sözdizimi

> **IF** *İfade1*\
> *IF-deyimleri*\
> ⟦**ElseIf** *İfade2*\
> *ElseIf-deyimlerini*⟧ \
> ⟦**ELSE**\
> *Else-deyimler*⟧ \
> **ENDIF**

## <a name="remarks"></a>Açıklamalar

Şu yönergeler [ElseIf](elseif-masm.md): **ELSEIFB**, **elseifdef**, **elseifdıf**, **elseifdifi**, **ELSEIFE**, **elseıfidn**, **elseıfidnı**, **elseifnb**ve **elseifndef**için kullanılabilir olabilir. İsteğe bağlı olarak, önceki ifade false ise *Else deyimlerini* ayrıştırır. İfadelerin derleme zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
