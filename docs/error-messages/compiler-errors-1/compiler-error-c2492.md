---
title: "Derleyici Hatası C2492 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2492
dev_langs: C++
helpviewer_keywords: C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68268be94897e3c648e95185877dec9e276355c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2492"></a>Derleyici Hatası C2492
'*değişkeni*': iş parçacığı depolama süresi verilerle dll arabirimi olmayabilir    
  
 Değişkeni ile bildirilmiş [iş parçacığı](../../cpp/thread.md) özniteliği ve DLL ile arabirim. Adresini `thread` bir DLL içeri veya dışarı aktarma bağlanamaz şekilde değişkeni çalışma zamanına kadar değil bilinen.  
  
 Aşağıdaki örnek C2492 oluşturur:  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```