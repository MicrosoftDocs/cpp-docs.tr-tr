---
title: "Derleyici Hatası C3270 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3270
dev_langs: C++
helpviewer_keywords: C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 326f53f06c6cc4d93eb85f265df161c7b2b86535
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3270"></a>Derleyici Hatası C3270
'field': FieldOffset özniteliği yalnızca StructLayout(Explicit) bağlamında kullanılabilir, bu durumda, gerekli  
  
Bir alan ile işaretlenmiş **FieldOffset**, yalnızca izin verilen zaman **StructLayout(Explicit)** etkili olur.  
  
Aşağıdaki örnek C3270 oluşturur:  
  
```  
// C3270_2.cpp  
// compile with: /clr /c  
using namespace System::Runtime::InteropServices;  
  
[ StructLayout(LayoutKind::Sequential) ]  
// try the following line instead  
// [ StructLayout(LayoutKind::Explicit) ]  
public value struct MYUNION  
{  
   [FieldOffset(0)] int a;   // C3270  
   // ...  
};  
```  
