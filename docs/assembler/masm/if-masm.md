---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: ed7b9e63bb19dcc16539dbdaaf1f6a7f16566b3c
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397459"
---
# <a name="if-masm"></a>IF (MASM)

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

Şu yönergeler [ElseIf](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **elseifdef**, **elseifdıf**, **elseifdifi**, **ELSEIFE**, **elseıfidn**, **elseıfidnı**, **elseifnb**ve **elseifndef**için kullanılabilir olabilir. İsteğe bağlı olarak, önceki ifade false ise *Else deyimlerini* ayrıştırır. İfadelerin derleme zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
