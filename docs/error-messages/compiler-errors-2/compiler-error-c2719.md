---
title: Derleyici Hatası C2719 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee8779db363c506d2f4ad884e15f78ba8231caa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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