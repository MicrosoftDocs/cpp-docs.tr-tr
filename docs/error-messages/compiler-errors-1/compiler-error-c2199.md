---
title: "Derleyici Hatası c2199 arasındaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2199
dev_langs: C++
helpviewer_keywords: C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dffccd5d4489581e21b1e7140b4790312d5be266
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2199"></a>Derleyici Hatası c2199 arasındaki
sözdizimi hatası: bulundu ' tanımlayıcısı (' genel kapsamlı (yönelik bir bildirim oldu mu?)  
  
 Belirtilen bağlam bir sözdizimi hatası nedeniyle. Hatalı bildirim sözdizimi olabilir.  
  
 Aşağıdaki örnek c2199 arasındaki oluşturur:  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```