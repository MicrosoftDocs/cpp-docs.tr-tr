---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: fc66338d90b54ecb12ef3ab1aa56214fb445cb13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397562"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Defines one or more external variables, labels, or symbols called *name* whose type is *type*.

## <a name="syntax"></a>Sözdizimi

> **EXTERN** ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ⟦ __,__ ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ...⟧

## <a name="remarks"></a>Açıklamalar

The *type* can be [ABS](../../assembler/masm/operator-abs.md), which imports *name* as a constant. Same as [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
