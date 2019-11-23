---
title: .SAFESEH
ms.date: 11/05/2019
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: df9798800da293e5e0b4f545a8442380b7ff9408
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397991"
---
# <a name="safeseh-32-bit-masm"></a>.SAFESEH (32-bit MASM)

Registers a function as a structured exception handler. (32-bit MASM only.)

## <a name="syntax"></a>Sözdizimi

> **.SAFESEH** *identifier*

## <a name="remarks"></a>Açıklamalar

*identifier* must be the ID for a locally defined [PROC](../../assembler/masm/proc.md) or [EXTRN](../../assembler/masm/extrn.md) PROC. A [LABEL](../../assembler/masm/label-masm.md) is not allowed. The .SAFESEH directive requires the [/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe command-line option.

For more information about structured exception handlers, see [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

For example, to register a safe exception handler, create a new MASM file (as follows), assemble with /safeseh, and add it to the linked objects.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
