---
title: "Derleyici Uyarısı (düzey 4) C4324 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4324
dev_langs:
- C++
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ef3e94e84621de6cd19bf7abba9c3d21b8d3eef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4324"></a>Derleyici Uyarısı (düzey 4) C4324
'struct_name': yapısı nedeniyle __declspec(align()) doldurulan  
  
 Doldurma, bir yapı sonunda eklenen, belirttiğiniz çünkü bir [__declspec(align)](../../cpp/align-cpp.md) değeri.  
  
 Örneğin, aşağıdaki kod C4324 oluşturur:  
  
```  
// C4324.cpp  
// compile with: /W4  
struct __declspec(align(32)) A  
{  
   char a;  
};   // C4324  
  
int main()  
{  
}  
```