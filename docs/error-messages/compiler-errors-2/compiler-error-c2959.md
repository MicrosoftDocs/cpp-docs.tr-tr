---
title: Derleyici Hatası C2959 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2959
dev_langs:
- C++
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ad7d4714e3f57f490fa8c1826b3c5bd4591a99f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2959"></a>Derleyici Hatası C2959
Genel sınıf veya işlevi bir şablon üyesi olmayabilir  
  
 Daha fazla bilgi için bkz: [Windows çalışma zamanı ve yönetilen şablonlar](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) ve [genel türler](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2959 oluşturur.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```