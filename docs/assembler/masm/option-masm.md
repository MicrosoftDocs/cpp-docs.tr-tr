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

Assembler özelliklerini etkinleştirip devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **Seçenek** *optionlist*

## <a name="remarks"></a>Açıklamalar

Kullanılabilir seçenekler şunlardır:

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**BENZETI**|
|**NOEMULATOR**|**KAPANıŞ**|**EXPR16**|**EXPR32**|
|**DILDIR**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOANAHTAR sözcüğü**|**NOSIGNEXTEND**|**KONUMU**|
|**ESKIMAKROLAR**|**NOOLDMACROS**|**OLDYAPıLAR**|**NOOLDYAPıLAR**|
|**PROC**|**BAŞLANGıÇ**|**ÖZELLIĞININ**|**NOREADONLY**|
|**YAYıL**|**NOKAPSAMLıDıR**|**SEGMENT**|**SETIF2**.|

DIL sözdizimi **:** <em>x</em>, burada *x* C, SYSCALL, stdcall, Pascal, FORTRAN veya BASIC 'ten biridir.  SYSCALL, PASCAL, FORTRAN ve BASIC, ile birlikte kullanıldığında desteklenmez [. düz MODEL](../../assembler/masm/dot-model.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
