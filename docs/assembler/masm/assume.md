---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 73ef8bcc33087a56747b80f94482fcd6c50e3bf6
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399262"
---
# <a name="assume-32-bit-masm"></a>ASSUME (32-bit MASM)

Enables error checking for register values. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **ASSUME**  *segregister* __:__ *name* ⟦ __,__ *segregister* __:__ *name*...⟧\
> **ASSUME**  *dataregister* __:__ *type* ⟦ __,__ *dataregister* __:__ *type*...⟧\
> **ASSUME**  *register* __:ERROR__ ⟦ __,__ *register* __:ERROR__...⟧\
> **ASSUME**  ⟦*register* __:__ ⟧**NOTHING** ⟦ __,__ *register* __:NOTHING__...⟧

## <a name="remarks"></a>Açıklamalar

After an **ASSUME** is put into effect, the assembler watches for changes to the values of the given registers. **ERROR** generates an error if the register is used. **NOTHING** removes register error checking. You can combine different kinds of assumptions in one statement.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
