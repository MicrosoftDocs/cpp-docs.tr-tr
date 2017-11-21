---
title: "Derleyici Hatası C3363 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3363
dev_langs: C++
helpviewer_keywords: C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e0601fed8638d6af814404517f495136a5d7d8d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3363"></a>Derleyici Hatası C3363
'type': 'TypeID' yalnızca bir türü için uygulanabilir  
  
 [TypeID](../../windows/typeid-cpp-component-extensions.md) işleci yanlış kullanıldı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3363 oluşturur.  
  
```  
// C3363.cpp  
// compile with: /clr  
int main() {  
   System::typeid;   // C3363  
}  
```