---
title: "Derleyici Hatası C2632 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03a6d75ab9af6cd45ef982ff9d2e12640266c1b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2632"></a>Derleyici Hatası C2632
'type1 'type2' tarafından izlenen' geçersiz  
  
 Bu hata var. kod iki tür tanımlayıcıları arasında eksikse neden olabilir.  
  
 Aşağıdaki örnek C2632 oluşturur:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Bu hata, Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucunda de oluşturulabilir. `bool`uygun türde sunulmuştur. Önceki sürümlerde, `bool` bir typedef oldu ve bu adı taşıyan tanımlayıcıları oluşturabilirsiniz.  
  
 Aşağıdaki örnek C2632 oluşturur:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Böylece kodu Visual C++, Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli bu hatayı gidermek için tanımlayıcı yeniden adlandırın.