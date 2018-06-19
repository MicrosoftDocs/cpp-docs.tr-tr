---
title: Derleyici Hatası C3272 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39900d11e7f6be25e8c9b701a52ff726807a4828
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254163"
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
