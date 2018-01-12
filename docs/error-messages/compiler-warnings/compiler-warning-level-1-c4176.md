---
title: "Derleyici Uyarısı (düzey 1) C4176 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4176
dev_langs: C++
helpviewer_keywords: C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b93ac22f3fa1df466dc7b5521bdc87f25210fb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4176"></a>Derleyici Uyarısı (düzey 1) C4176
'alt': #pragma bileşen tarayıcı için bilinmeyen bir alt bileşen  
  
 **Bileşen** pragma geçersiz bir alt bileşen içerir. Belirli bir ad başvurular dışlamak için kullanmalısınız **başvuruları** adından önce seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// C4176.cpp  
// compile with: /W1 /LD  
#pragma component(browser, off, i)  // C4176  
#pragma component(browser, off, references, i) // ok  
```