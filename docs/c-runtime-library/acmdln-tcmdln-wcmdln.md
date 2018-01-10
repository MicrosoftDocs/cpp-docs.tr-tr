---
title: _acmdln, _tcmdln, _wcmdln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcmdln
- _acmdln
apilocation: msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
dev_langs: C++
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8250822adb801365fca826f33899a7ae3d1d06a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 Bu CRT iç değişkenler tam komut satırı depolar. Dışarı aktarılan sembolleri için CRT gösterilir, ancak kodunuzda kullanılmak üzere tasarlanmamıştır. `_acmdln`verileri bir karakter dizisi olarak depolar. `_wcmdln`verileri bir geniş karakter dizesi depolar. `_tcmdln`olarak tanımlanabilir `_acmdln` veya `_wcmdln`uygun olduğu bağlı olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Değişkenler](../c-runtime-library/global-variables.md)