---
title: Derleyici Hatası C2504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bac0f8f28955af172590535568289182c3489d6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229524"
---
# <a name="compiler-error-c2504"></a>Derleyici Hatası C2504
'class': temel tanımsız sınıfı  
  
 Taban sınıfı bildirilen ancak hiçbir zaman tanımlı.  Olası nedenler:  
  
1.  İçerme dosyası eksik.  
  
2.  Dış temel sınıf bildirilmemiş ile [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
 Aşağıdaki örnek C2504 oluşturur:  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 TAMAM  
  
```  
class C{};  
class D : public C {};  
```