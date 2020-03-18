---
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 6e63f5c8075b3c94370ad8863d224c097cf0ecdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440753"
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
