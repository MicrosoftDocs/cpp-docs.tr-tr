---
title: "Derleyici Uyarısı C4986 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4986
dev_langs: C++
helpviewer_keywords: C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c83c03d746949edd880e815a578dc437e9d1d1ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4986"></a>Derleyici Uyarısı C4986
'function': özel durum belirtimi önceki bildirimi eşleşmiyor  
  
 Bir bildirim ve diğer bir özel durum belirtimi olduğunda bu uyarı oluşturulabilir.  
  
 Varsayılan olarak, C4986 kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4986 oluşturur.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1()  
{  
    // ...  
}    
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu uyarıyı ortadan kaldırır.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1() throw (X*)  
{  
    // ...  
}    
```