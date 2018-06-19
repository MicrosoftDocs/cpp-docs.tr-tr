---
title: Derleyici Hatası C2632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3bc07c404a1f4d667045fdfea24009e7d20ad69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232639"
---
# <a name="compiler-error-c2632"></a>Derleyici Hatası C2632
'type1 'type2' tarafından izlenen' geçersiz  
  
 Bu hata var. kod iki tür tanımlayıcıları arasında eksikse neden olabilir.  
  
 Aşağıdaki örnek C2632 oluşturur:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Bu hata, Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucunda de oluşturulabilir. `bool` uygun türde sunulmuştur. Önceki sürümlerde, `bool` bir typedef oldu ve bu adı taşıyan tanımlayıcıları oluşturabilirsiniz.  
  
 Aşağıdaki örnek C2632 oluşturur:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Böylece kodu Visual C++, Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli bu hatayı gidermek için tanımlayıcı yeniden adlandırın.