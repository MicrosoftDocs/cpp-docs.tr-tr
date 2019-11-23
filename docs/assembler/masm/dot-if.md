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
# <a name="if-32-bit-masm"></a>.IF (32-bit MASM)

Generates code that tests *condition1* (for example, AX > 7) and executes the *statements* if that condition is true. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **.IF** *condition1*\
> *statements*\
> ⟦ **.ELSEIF** *condition2*\
> *statements*⟧\
> ⟦ **.ELSE**\
> *statements*⟧\
> **.ENDIF**

## <a name="remarks"></a>Açıklamalar

If a [.ELSE](../../assembler/masm/dot-else.md) follows, its statements are executed if the original condition was false. Note that the conditions are evaluated at run time.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
