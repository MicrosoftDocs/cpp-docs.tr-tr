---
title: "Derleyici Uyarısı (düzey 1) C4965 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4965
dev_langs:
- C++
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f92cc2115bc35c669b4d45784e1e1d79875551e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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