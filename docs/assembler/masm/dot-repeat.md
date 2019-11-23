---
title: .REPEAT
ms.date: 11/05/2019
f1_keywords:
- .REPEAT
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
ms.openlocfilehash: 2a447cb13fa78b0f2ad3cf61e2d0ff77a5b8cfd9
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398003"
---
# <a name="repeat-32-bit-masm"></a>.REPEAT (32-bit MASM)

Generates code that repeats execution of the block of *statements* until *condition* becomes true. [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md), which becomes true when CX is zero, may be substituted for [.UNTIL](../../assembler/masm/dot-until.md). The *condition* is optional with **.UNTILCXZ**. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **.REPEAT**\
> *statements*\
> **.UNTIL** *condition*

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
