---
title: SEÇENEĞİ (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09db749baf09525957faaf8af99434cc9775d0e7
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678051"
---
# <a name="option-masm"></a>OPTION (MASM)

Etkinleştirir ve derleyici özelliklerini devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> SEÇENEK *optionlist*

## <a name="remarks"></a>Açıklamalar

Mevcut seçenekler şunlardır:

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ÖYKÜNÜCÜ**|
|**NOEMULATOR**|**KAPANIŞ**|**EXPR16**|**EXPR32**|
|**DİL**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**UZAKLIK**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**GİRİŞ**|**SALT OKUNUR**|**NOREADONLY**|
|**KAPSAMLI**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

Dilin sözdizimi **seçeneği dil:**<em>x</em>burada *x* C, SYSCALL, STDCALL, PASCAL, FORTRAN veya temel biridir.  SYSCALL, PASCAL, FORTRAN ve temel ile desteklenmez ile kullanılan [. MODEL](../../assembler/masm/dot-model.md) DÜZ.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>