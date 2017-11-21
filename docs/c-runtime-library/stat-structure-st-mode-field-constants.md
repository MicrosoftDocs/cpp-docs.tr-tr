---
title: "_stat yapı st_mode alanı sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
dev_langs: C++
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eb6277eea45aec64c285c3e2780d65be0224ce11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stat-structure-stmode-field-constants"></a>_stat Yapı st_mode Alanı Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri dosya türünü belirtmek için kullanılan **st_mode** alanını [_stat yapı](../c-runtime-library/standard-types.md).  
  
 Bit maskesi sabitleri aşağıda açıklanmıştır:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_S_IFMT`|Dosya türü maskesi|  
|`_S_IFDIR`|Dizin|  
|`_S_IFCHR`|Karakter özel (bir cihaz gösterir ayarlayın)|  
|`_S_IFREG`|Normal|  
|`_S_IREAD`|Okuma izni, sahibi|  
|`_S_IWRITE`|Yazma izni, sahibi|  
|`_S_IEXEC`|İzni yürütme/arama sahibi|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_stat, _wstat işlevleri](../c-runtime-library/reference/stat-functions.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [Standart Türler](../c-runtime-library/standard-types.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)