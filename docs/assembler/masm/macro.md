---
title: MACRO
ms.date: 08/30/2018
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 860d538a2f461db1d5fd6bb24d078f644af2156f
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397239"
---
# <a name="macro"></a>MACRO

Marks a macro block called *name* and establishes *parameter* placeholders for arguments passed when the macro is called.

## <a name="syntax"></a>Sözdizimi

> *name*  **MACRO** ⟦*parameter* ⟦ **:REQ** | :=*default* |  **:VARARG**⟧ ...⟧\
> *statements*\
> **ENDM** ⟦*value*⟧

## <a name="remarks"></a>Açıklamalar

A macro function returns *value* to the calling statement.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
