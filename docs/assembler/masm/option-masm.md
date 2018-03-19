---
title: "SEÇENEĞİ (MASM) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d8e8049ecea3775b9df85eb1d5c8ee5e94a9243
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
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
|**PROC**|**GİRİŞ**|**READONLY**|**NOREADONLY**|  
|**KAPSAMLI**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 DİLİ sözdizimi **seçeneği dil:***x*, burada *x* C, SYSCALL, STDCALL, PASCAL, FORTRAN veya BASIC biridir.  SYSCALL, PASCAL, FORTRAN ve BASIC desteklenmez ile birlikte kullanılan [. MODEL](../../assembler/masm/dot-model.md) DÜZ.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)