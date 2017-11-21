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
ms.openlocfilehash: 0463c762cec98f60b0e8a3811f1f5c9b7e2cdea7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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