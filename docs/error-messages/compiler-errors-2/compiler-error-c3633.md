---
title: "Derleyici Hatası C3633 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3633
dev_langs: C++
helpviewer_keywords: C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b88a5008b0703f99d7eefa3892b4ee263fea9d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3633"></a>Derleyici Hatası C3633
Yönetilen 'type' üyesi olarak 'üyesi' tanımlanamıyor  
  
CLR başvuru sınıf veri üyeleri POD C++ türünde olamaz.  Yalnızca bir CLR türü POD yerel tür örneğini oluşturabilirsiniz.  Örneğin, bir POD türü kopya oluşturucu veya atama işleci içeremez.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3633 oluşturur.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
