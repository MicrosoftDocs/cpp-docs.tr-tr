---
title: "Derleyici Hatası C3272 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3272
dev_langs: C++
helpviewer_keywords: C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8447e7eb07cea90da5076fa2c7bf6fe950baf5e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3272"></a>Derleyici Hatası C3272
'simgesi': simge türü typename StructLayout(LayoutKind::Explicit) ile tanımlanan bir üyesi olarak FieldOffset, gerektirir  
  
Zaman `StructLayout(LayoutKind::Explicit)` etkili, alanları işaretlenen, sahip olduğu `FieldOffset`.  
  
Aşağıdaki örnek C3272 oluşturur:  
  
```  
// C3272_2.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
ref struct X  
{  
   int data_;   // C3272  
   // try the following line instead  
   // [FieldOffset(0)] int data_;  
};  
```  
