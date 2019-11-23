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

Grants assembly of *ifstatements* if *expression1* is true (nonzero) or *elseifstatements* if *expression1* is false (0) and *expression2* is true.

## <a name="syntax"></a>Sözdizimi

> **IF** *expression1*\
> *if-statements*\
> ⟦**ELSEIF** *expression2*\
> *elseif-statements*⟧\
> ⟦**ELSE**\
> *else-statements*⟧\
> **ENDIF**

## <a name="remarks"></a>Açıklamalar

The following directives may be substituted for [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, and **ELSEIFNDEF**. Optionally, assembles *else-statements* if the previous expression is false. Note that the expressions are evaluated at assembly time.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
