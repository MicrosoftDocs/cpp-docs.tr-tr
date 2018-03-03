---
title: "Derleyici Hatası C2847 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1ee4fd957f72c60e30641b1127796bebadb009
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2847"></a>Derleyici Hatası C2847
sizeof yönetilen veya WinRT türü 'sınıfı' uygulayamazsınız.  
  
 [Sizeof](../../cpp/sizeof-operator.md) işleci derleme zamanında bir nesnenin değerini alır. Yönetilen boyutunu veya WinRT sınıfı, arabirim veya değer türü dinamiktir ve böylece derleme zamanında bilinen olamaz.  
  
 Örneğin, aşağıdaki örnek C2847 oluşturur:  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  
