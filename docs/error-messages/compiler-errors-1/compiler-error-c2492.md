---
title: "Derleyici Hatası C2492 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5410af24b5300b2c03aa0ed4e121abceb6d6d483
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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