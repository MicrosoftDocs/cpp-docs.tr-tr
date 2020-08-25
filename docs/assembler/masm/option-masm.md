---
title: OPTION (MASM)
ms.date: 07/15/2020
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 3d5bef52106b38487d1a2be248cff274f39e009c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830846"
---
# <a name="option"></a>OPTION

Assembler özelliklerini etkinleştirip devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **`OPTION`***seçenek-liste*

## <a name="remarks"></a>Açıklamalar

Mevcut seçenekler şunlardır:

:::row:::
   :::column span="":::
      **`CASEMAP`**\
      **`DOTNAME`**\
      **`NODOTNAME`**\
      **`EMULATOR`**\
      **`NOEMULATOR`**\
      **`EPILOGUE`**\
      **`EXPR16`**
   :::column-end:::
   :::column span="":::
      **`EXPR32`**\
      **`LANGUAGE`**\
      **`LJMP`**\
      **`NOLJMP`**\
      **`M510`**\
      **`NOM510`**\
      **`NOKEYWORD`**
   :::column-end:::
   :::column span="":::
      **`NOSIGNEXTEND`**\
      **`OFFSET`**\
      **`OLDMACROS`**\
      **`NOOLDMACROS`**\
      **`OLDSTRUCTS`**\
      **`NOOLDSTRUCTS`**\
      **`PROC`**
   :::column-end:::
   :::column span="":::
      **`PROLOGUE`**\
      **`READONLY`**\
      **`NOREADONLY`**\
      **`SCOPED`**\
      **`NOSCOPED`**\
      **`SEGMENT`**\
      **`SETIF2`**
   :::column-end:::
:::row-end:::

Dili için sözdizimi,,,,, **`OPTION LANGUAGE:`** _`x`_ *`x`* veya ' nin biridir **`C`** **`SYSCALL`** **`STDCALL`** **`PASCAL`** **`FORTRAN`** **`BASIC`** . **`SYSCALL`**, **`PASCAL`** , **`FORTRAN`** ve **`BASIC`** ile desteklenmez [`.MODEL`](dot-model.md) **`FLAT`** .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
