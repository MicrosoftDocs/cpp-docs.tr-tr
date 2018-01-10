---
title: "Derleyici Hatası C2283 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2283
dev_langs: C++
helpviewer_keywords: C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b71e1217c1ee5f25c348ec05069b76a591a0f98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2283"></a>Derleyici Hatası C2283
'tanımlayıcısı': Saf belirleyici veya Özet geçersiz kılma tanımlayıcısı adlandırılmamış yapısı üzerinde izin verilmiyor  
  
 Bir adlandırılmamış sınıf veya yapı üyesi işlevinin izin bir saf tanımlayıcısı ile bildirilir.  
  
 Aşağıdaki örnek C2283 oluşturur:  
  
```  
// C2283.cpp  
// compile with: /c  
struct {  
   virtual void func() = 0;   // C2283  
};  
struct T {  
   virtual void func() = 0;   // OK  
};  
```