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
ms.openlocfilehash: 148e3e6035304eb155a478e5971defd9a0a55120
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081
'simgesi': dosya adı çok uzun  
  
 Bir dosya yol uzunluğunu aşıyor `_MAX_PATH` (STDLIB.h tarafından 260 karakter olarak tanımlanır). Dosya adını kısaltın.  
  
 CL.exe bir kısa dosya adı ile çağırırsanız, derleyici bir tam yol oluşturmak gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin oluşturmasına neden olabilir:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```