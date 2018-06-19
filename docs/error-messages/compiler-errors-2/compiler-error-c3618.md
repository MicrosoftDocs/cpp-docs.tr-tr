---
title: Derleyici Hatası C3618 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3618
dev_langs:
- C++
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78fb928c9e86105c97f1feb37ae8765c5e68b153
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257263"
---
# <a name="compiler-error-c3618"></a>Derleyici Hatası C3618
'function': DllImport işaretli bir yöntem tanımlanamıyor  
  
 Bir yöntem olarak <xref:System.Runtime.InteropServices.DllImportAttribute> tanımlanır belirtilen. DLL.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3618 oluşturur.  
  
```  
// C3618.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED   
void Func();   
  
void Func() {}   // C3618, remove this function definition to resolve  
```