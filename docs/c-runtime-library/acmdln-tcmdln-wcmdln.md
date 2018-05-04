---
title: _acmdln, _tcmdln, _wcmdln | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _wcmdln
- _acmdln
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
dev_langs:
- C++
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 141e261af618cc6058a2a731b70e824582be303b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="acmdln-tcmdln-wcmdln"></a>_acmdln, _tcmdln, _wcmdln
İç CRT genel değişkeni. Komut satırı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char * _acmdln;  
wchar_t * _wcmdln;  
  
#ifdef WPRFLAG  
   #define _tcmdln _wcmdln  
#else  
   #define _tcmdln _acmdln  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu CRT iç değişkenler tam komut satırı depolar. Dışarı aktarılan sembolleri için CRT gösterilir, ancak kodunuzda kullanılmak üzere tasarlanmamıştır. `_acmdln` verileri bir karakter dizisi olarak depolar. `_wcmdln` verileri bir geniş karakter dizesi depolar. `_tcmdln` olarak tanımlanabilir `_acmdln` veya `_wcmdln`uygun olduğu bağlı olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Değişkenler](../c-runtime-library/global-variables.md)