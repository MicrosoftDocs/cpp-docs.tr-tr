---
title: "SEÇENEĞİ (MASM) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="option-masm"></a>OPTION (MASM)
Etkinleştirir ve assembler özelliklerini devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Mevcut seçenekler şunlardır:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ÖYKÜNÜCÜSÜ**|  
|**NOEMULATOR**|**EPİLOG**|**EXPR16**|**EXPR32**|  
|**DİL**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**UZAKLIK**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**GİRİŞ**|**SALT OKUNUR**|**NOREADONLY**|  
|**KAPSAMLI**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 DİLİ sözdizimi **seçeneği dil:***x*, burada *x* C, SYSCALL, STDCALL, PASCAL, FORTRAN veya BASIC biridir.  SYSCALL, PASCAL, FORTRAN ve BASIC desteklenmez ile birlikte kullanılan [. MODEL](../../assembler/masm/dot-model.md) DÜZ.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)