---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: a8215bf1f816baa490a768fb2cab0b3c2e53e20b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217263"
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