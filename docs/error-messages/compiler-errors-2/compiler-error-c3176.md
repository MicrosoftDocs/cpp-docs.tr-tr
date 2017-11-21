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
ms.openlocfilehash: ce046573ebeaf68f3b48d0e3d096b172bf26a66c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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