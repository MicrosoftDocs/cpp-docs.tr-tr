---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 0f90ab0115c3dde894d468bbbe60ffa0193b8336
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395176"
---
# <a name="option-masm"></a>OPTION (MASM)

Enables and disables features of the assembler.

## <a name="syntax"></a>Sözdizimi

> **OPTION** *optionlist*

## <a name="remarks"></a>Açıklamalar

Available options include:

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**PROLOGUE**|**READONLY**|**NOREADONLY**|
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

The syntax for LANGUAGE is **OPTION LANGUAGE:** <em>x</em>, where *x* is one of C, SYSCALL, STDCALL, PASCAL, FORTRAN, or BASIC.  SYSCALL, PASCAL, FORTRAN, and BASIC are not supported with used with [.MODEL](../../assembler/masm/dot-model.md) FLAT.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
