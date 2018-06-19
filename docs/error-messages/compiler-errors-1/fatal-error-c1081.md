---
title: Önemli hata C1081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5ea18ff3f2714d9621d4372cf541be2f9b225a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230528"
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081
'simgesi': dosya adı çok uzun  
  
 Bir dosya yol uzunluğunu aşıyor `_MAX_PATH` (STDLIB.h tarafından 260 karakter olarak tanımlanır). Dosya adını kısaltın.  
  
 CL.exe bir kısa dosya adı ile çağırırsanız, derleyici bir tam yol oluşturmak gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin oluşturmasına neden olabilir:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```