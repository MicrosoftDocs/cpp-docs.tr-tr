---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: a5175252364918ca218e81536b29f084f7fd19cc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397305"
---
# <a name="invoke-32-bit-masm"></a>INVOKE (32-bit MASM)

Calls the procedure at the address given by *expression*, passing the arguments on the stack or in registers according to the standard calling conventions of the language type. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **INVOKE** *expression* ⟦ __,__ *argument* ...⟧

## <a name="remarks"></a>Açıklamalar

Each argument passed to the procedure may be an expression, a register pair, or an address expression (an expression preceded by **ADDR**).

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](../../assembler/masm/directives-reference.md)
