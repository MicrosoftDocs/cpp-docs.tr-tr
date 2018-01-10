---
title: "Derleyici Hatası C2719 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2719
dev_langs: C++
helpviewer_keywords: C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554a8c2655e82e7d793966738474338aab934168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2719"></a>Derleyici Hatası C2719
'parametresi': __declspec(align('#')) ile biçimsel parametresi olmaz hizalı  
  
 [Hizala](../../cpp/align-cpp.md) `__declspec` değiştirici işlevi parametrelere izin verilmez. İşlev parametresi hizalama kullanılan çağırma tarafından denetlenir. Daha fazla bilgi için bkz: [çağırma kuralları](../../cpp/calling-conventions.md).  
  
 Aşağıdaki örnek C2719 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```