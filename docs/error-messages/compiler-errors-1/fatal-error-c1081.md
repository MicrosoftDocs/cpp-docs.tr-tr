---
title: "Önemli hata C1081 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1081
dev_langs: C++
helpviewer_keywords: C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bac4aaf0d4aebcbc34f74b6ccb91170fd4224e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081
'simgesi': dosya adı çok uzun  
  
 Bir dosya yol uzunluğunu aşıyor `_MAX_PATH` (STDLIB.h tarafından 260 karakter olarak tanımlanır). Dosya adını kısaltın.  
  
 CL.exe bir kısa dosya adı ile çağırırsanız, derleyici bir tam yol oluşturmak gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin oluşturmasına neden olabilir:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```