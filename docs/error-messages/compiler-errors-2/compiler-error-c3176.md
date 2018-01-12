---
title: "Derleyici Hatası C3176 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3176
dev_langs: C++
helpviewer_keywords: C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6efdea50fbc807175dbe67af27835dea9de7363e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3176"></a>Derleyici Hatası C3176
'type': yerel değerin türü bildiremezsiniz  
  
 Bir sınıf, yalnızca genel kapsamlı bir değer türü olarak bildirilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3176 oluşturur.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```