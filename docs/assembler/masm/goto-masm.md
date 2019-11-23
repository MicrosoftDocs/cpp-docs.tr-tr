---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 424ff295fe37e7c5ff02897a01b99a7c75876f85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397490"
---
# <a name="goto-masm"></a>GOTO (MASM)

Transfers assembly to the line marked **:** _macrolabel_.

## <a name="syntax"></a>Sözdizimi

> **GOTO** *macrolabel*

## <a name="remarks"></a>Açıklamalar

**GOTO** is permitted only inside [MACRO](macro.md), [FOR](for-masm.md), [FORC](forc.md), [REPEAT](repeat.md), and [WHILE](while-masm.md) blocks. The *macrolabel* target must be the only directive on the line and must be preceded by a leading colon.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
