---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 063689087b6114f9a2d544ef0b459bf594da3cc4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398819"
---
# <a name="comm"></a>COMM

Creates a communal variable with the attributes specified in *definition*.

## <a name="syntax"></a>Sözdizimi

> **COMM** *definition* ⟦ __,__ *definition* ...⟧

## <a name="remarks"></a>Açıklamalar

Communal variables are allocated by the linker, and can't be initialized. This means that you can't depend on the location or sequence of such variables.

Each *definition* has the following form:

⟦*langtype*⟧ ⟦⦃**NEAR** &#124; **FAR**⦄⟧ _label_ **:** _type_⟦ **:** _count_⟧

The optional *langtype* sets the naming conventions for the name that follows. It overrides any language specified by the **.MODEL** directive. The optional **NEAR** or **FAR** override the current memory model. The *label* is the name of the variable. The *type* can be any type specifier ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), and so on) or an integer specifying the number of bytes. The optional *count* specifies the number of elements in the declared data object; the default is one.

## <a name="example"></a>Örnek

This example creates an array of 512 BYTE elements:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
