---
title: "Derleyici Hatası C3417 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3417
dev_langs: C++
helpviewer_keywords: C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 341f6e74c5d0815c4202a340bff5c72631940f85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3417"></a>Derleyici Hatası C3417
'member': değer türleri, kullanıcı tanımlı özel üye işlevleri içeremez  
  
 Değer türleri varsayılan örnek oluşturucu, yıkıcı veya kopya Oluşturucu gibi işlevler içeremez.  
  
 Aşağıdaki örnek C3517 oluşturur:  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```