---
description: 'Hakkında daha fazla bilgi edinin:'
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 09b4bd09155ef848ad165b4e8b0d3a093ade0008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130215"
---
# <a name="if"></a>IF

*İfade1 true* ise (sıfır dışında) veya *İfade1* yanlış (0) *ise ve* *İfade2* true ise, *ifdeyimlerin* derlemesini verir.

## <a name="syntax"></a>Syntax

> **IF** *İfade1*\
> *if-deyimleri*\
> ⟦**ElseIf** *İfade2*\
> *ElseIf-deyimlerini*⟧ \
> ⟦**Else**\
> *Else-deyimler*⟧ \
> **ENDIF**

## <a name="remarks"></a>Açıklamalar

Şu yönergeler [ElseIf](elseif-masm.md): **ELSEIFB**, **elseifdef**, **elseifdıf**, **elseifdifi**, **ELSEIFE**, **elseıfidn**, **elseıfidnı**, **elseifnb** ve **elseifndef** için kullanılabilir olabilir. İsteğe bağlı olarak, önceki ifade false ise *Else deyimlerini* ayrıştırır. İfadelerin derleme zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
