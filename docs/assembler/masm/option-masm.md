---
title: OPTION (MASM)
ms.date: 12/17/2019
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: bd50ac2e051db7f02ac077054e5856524745df54
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318754"
---
# <a name="option"></a>OPTION

Assembler özelliklerini etkinleştirip devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **Seçenek** *optionlist*

## <a name="remarks"></a>Açıklamalar

Mevcut seçenekler şunlardır:

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**BENZETI**|
|**NOEMULATOR**|**KAPANıŞ**|**EXPR16**|**EXPR32**|
|**DILDIR**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOANAHTAR sözcüğü**|**NOSIGNEXTEND**|**KONUMU**|
|**ESKIMAKROLAR**|**NOOLDMACROS**|**OLDYAPıLAR**|**NOOLDYAPıLAR**|
|**PROC**|**BAŞLANGıÇ**|**ÖZELLIĞININ**|**NOREADONLY**|
|**YAYıL**|**NOKAPSAMLıDıR**|**SEGMENT**|**SETIF2**.|

DIL sözdizimi **:** <em>x</em>, burada *x* C, SYSCALL, stdcall, Pascal, FORTRAN veya BASIC 'ten biridir.  SYSCALL, PASCAL, FORTRAN ve BASIC, ile desteklenmez [. düz MODEL](dot-model.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
