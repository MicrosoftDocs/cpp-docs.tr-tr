---
title: "Derleyici Hatası C3672 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3672
dev_langs: C++
helpviewer_keywords: C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f01237ca5ac90ea3def4a6d2733ef8dd700bf738
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3672"></a>Derleyici Hatası C3672
Sözde yıkıcı ifade yalnızca bir işlev çağrısı bir parçası olarak kullanılabilir  
  
 Bir yıkıcı hatalı çağrıldı.  Daha fazla bilgi için bkz: [Yıkıcılar](../../cpp/destructors-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3672 oluşturur.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```