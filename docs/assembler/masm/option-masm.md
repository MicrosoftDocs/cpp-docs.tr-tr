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
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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