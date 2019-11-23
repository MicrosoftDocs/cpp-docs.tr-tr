---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 650c69be17c9271c343360edbb90f093841a1047
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398252"
---
# <a name="fpo-32-bit-masm"></a>.FPO (32-bit MASM)

The **.FPO** directive controls the emission of debug records to the .debug$F segment or section. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **.FPO** (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

### <a name="parameters"></a>Parametreler

*cdwLocals*\
Number of local variables, an unsigned 32 bit value.

*cdwParams*\
Size of the parameters in DWORDS, an unsigned 16 bit value.

*cbProlog*\
Number of bytes in the function prolog code, an unsigned 8 bit value.

*cbRegs*\
Number registers saved.

*fUseBP*\
Indicates whether the EBP register has been allocated. either 0 or 1.

*cbFrame*\
Indicates the frame type.  See [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) for more information.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
