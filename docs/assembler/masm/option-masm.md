---
title: OPTION (MASM)
ms.date: 07/15/2020
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: a614697a9d633628b02b59a7b810fa261887f859
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446443"
---
# <a name="option"></a>OPTION

Assembler özelliklerini etkinleştirip devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **`OPTION`***seçenek-liste*

## <a name="remarks"></a>Açıklamalar

Mevcut seçenekler şunlardır:

:::row:::
   :::column span="":::
      **`CASEMAP`**<br/>**`DOTNAME`**<br/>**`NODOTNAME`**<br/>**`EMULATOR`**<br/>**`NOEMULATOR`**<br/>**`EPILOGUE`**<br/>**`EXPR16`**
   :::column-end:::
   :::column span="":::
      **`EXPR32`**<br/>**`LANGUAGE`**<br/>**`LJMP`**<br/>**`NOLJMP`**<br/>**`M510`**<br/>**`NOM510`**<br/>**`NOKEYWORD`**
   :::column-end:::
   :::column span="":::
      **`NOSIGNEXTEND`**<br/>**`OFFSET`**<br/>**`OLDMACROS`**<br/>**`NOOLDMACROS`**<br/>**`OLDSTRUCTS`**<br/>**`NOOLDSTRUCTS`**<br/>**`PROC`**
   :::column-end:::
   :::column span="":::
      **`PROLOGUE`**<br/>**`READONLY`**<br/>**`NOREADONLY`**<br/>**`SCOPED`**<br/>**`NOSCOPED`**<br/>**`SEGMENT`**<br/>**`SETIF2`**
   :::column-end:::
:::row-end:::

Dili için sözdizimi,,,,, **`OPTION LANGUAGE:`** _`x`_ *`x`* veya ' nin biridir **`C`** **`SYSCALL`** **`STDCALL`** **`PASCAL`** **`FORTRAN`** **`BASIC`** . **`SYSCALL`**, **`PASCAL`** , **`FORTRAN`** ve **`BASIC`** ile desteklenmez [`.MODEL`](dot-model.md) **`FLAT`** .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
