---
title: "Önemli hata C1071 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1071
dev_langs: C++
helpviewer_keywords: C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cc8bafad2b85b4f5e733d052f5dcd1560398333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1071"></a>Önemli hata C1071
Beklenmeyen açıklamada bulunan dosya sonu  
  
 Derleyici, yorum taranırken dosya sonuna ulaşıldı.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Açıklama Sonlandırıcı eksik (* /).  
  
2.  Bir kaynak dosyasının son satırında bir yorum sonra yeni satır karakteri eksik.  
  
 Aşağıdaki örnek C1071 oluşturur:  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```