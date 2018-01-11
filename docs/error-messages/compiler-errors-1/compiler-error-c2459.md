---
title: "Derleyici Hatası C2459 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2459
dev_langs: C++
helpviewer_keywords: C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 702b7f29cf0fe8be51f073e66efe701824ab0793
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2459"></a>Derleyici Hatası C2459
'tanımlayıcısı': tanımlanıyorsa; Anonim bir üye olarak eklenemez  
  
 Sınıf, yapı veya birleşim kendi kapsamında anonim bir birleşim bir üyesi tarafından tanımlandı.  
  
 Aşağıdaki örnek C2459 oluşturur:  
  
```  
// C2459.cpp  
// compile with: /c  
class C {  
   union { int C; };   // C2459  
   union { int D; };  
};  
```