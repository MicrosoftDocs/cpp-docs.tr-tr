---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 469b49832c171ee78336a0c457f0d269acd3b59d
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397535"
---
# <a name="externdef"></a>EXTERNDEF

Defines one or more external variables, labels, or symbols called *name* whose type is *type*.

## <a name="syntax"></a>Sözdizimi

> **EXTERNDEF** ⟦*language-type*⟧ *name* __:__ *type* ⟦ __,__ ⟦*language-type*⟧ *name* __:__ *type* ...⟧

## <a name="remarks"></a>Açıklamalar

If *name* is defined in the module, it is treated as [PUBLIC](../../assembler/masm/public-masm.md). If *name* is referenced in the module, it is treated as [EXTERN](../../assembler/masm/extern-masm.md). If *name* is not referenced, it is ignored. The *type* can be [ABS](../../assembler/masm/operator-abs.md), which imports *name* as a constant. Normally used in include files.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
