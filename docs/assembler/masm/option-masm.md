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
ms.openlocfilehash: ab64740cd5f04b4a707a702f0bf39174907fc8fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)