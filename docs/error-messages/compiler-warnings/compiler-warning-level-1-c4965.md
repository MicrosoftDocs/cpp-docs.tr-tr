---
title: Derleyici Uyarısı (düzey 1) C4965 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4965
dev_langs:
- C++
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b731393471097fd3ba02979a48cd59513eaea9fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4965"></a>Derleyici Uyarısı (düzey 1) C4965
örtük kutusu tamsayı 0; nullptr veya açık atama kullanın  
  
 Visual C++ değer türlerini örtük kutulama özellikleri. C++ şimdi olur Kutulu int atama için Yönetilen Uzantılar kullanarak boş bir atama ile sonuçlandı bir yönerge  
  
 Daha fazla bilgi için bkz: [kutulama](../../windows/boxing-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4965 oluşturur.  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```