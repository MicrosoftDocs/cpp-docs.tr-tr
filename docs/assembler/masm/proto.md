---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 24ec2a9abc6c8b76fc81f6d412019296c53160f4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74394751"
---
# <a name="proto"></a>PROTO

Prototypes a function or procedure. You can call the function prototyped by the PROTO directive by using the [INVOKE](invoke.md) directive.

## <a name="syntax"></a>Sözdizimi

> *label* **PROTO** ⟦*distance*⟧ ⟦*language-type*⟧ ⟦ __,__ ⟦*parameter*⟧ __:__ *tag* ...⟧

### <a name="parameters"></a>Parametreler

*label*\
The name of the prototyped function.

*distance*\
(Optional) Used in 16-bit memory models to override the default and indicate **NEAR** or **FAR** calls.

*language-type*\
(Optional) Sets the calling and naming convention for procedures and public symbols. Supported conventions are:

- 32-bit **FLAT** model: **C**, **STDCALL**

- 16-bit models: **C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

*parameter*\
The optional name for a function parameter.

*tag*\
The type of a function parameter.

The *parameter* and *tag* parameters may appear multiple times, once for each passed argument.

## <a name="example"></a>Örnek

This sample shows a **PROTO** declaration for a function named `addup3` that uses a **NEAR** call to override the 16-bit model default for procedure calls, and uses the **C** calling convention for stack parameters and return values. It takes two arguments, a **WORD** and a **VARARG**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Ayrıca bkz.

[Directives Reference](directives-reference.md)\
[.MODEL Reference](dot-model.md)
