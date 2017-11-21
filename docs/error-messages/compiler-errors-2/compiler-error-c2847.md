---
title: "Derleyici Hatası C2847 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2847
dev_langs: C++
helpviewer_keywords: C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8406ea786def9c3241a0ae1de8743d53e91f96cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
