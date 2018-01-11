---
title: "Derleyici Hatası C2504 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2504
dev_langs: C++
helpviewer_keywords: C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b7843d69b7238bedb58d0232d64ff2d0a826d07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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