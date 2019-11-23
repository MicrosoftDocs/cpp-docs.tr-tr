---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: b0f047278f6250d5ef359f7992df4ea23f4bbd9b
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398042"
---
# <a name="pushframe"></a>.PUSHFRAME

Generates a `UWOP_PUSH_MACHFRAME` unwind code entry. If the optional *code* is specified, the unwind code entry is given a modifier of 1. Otherwise the modifier is 0.

## <a name="syntax"></a>Sözdizimi

> **.PUSHFRAME** ⟦*code*⟧;;

## <a name="remarks"></a>Açıklamalar

.PUSHFRAME allows ml64.exe users to specify how a frame function unwinds and is only allowed within the prologue, which extends from the [PROC](../../assembler/masm/proc.md) FRAME declaration to the [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) directive. These directives do not generate code; they only generate `.xdata` and `.pdata`. **.PUSHFRAME** should be preceded by instructions that actually implement the actions to be unwound. It is a good practice to wrap both the unwind directives and the code they are meant to unwind in a macro to ensure agreement.

For more information, see [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
