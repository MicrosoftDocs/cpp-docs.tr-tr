---
title: SEÇENEĞİ (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 4a2dcbc55d6a2d033cde3b6189618afd67bdc3fb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221515"
---
# <a name="option-masm"></a>OPTION (MASM)
Etkinleştirir ve derleyici özelliklerini devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
OPTION   
optionlist  
  
```  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)