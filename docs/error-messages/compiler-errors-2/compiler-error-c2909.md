---
title: "Derleyici Hatası C2909 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1786a868bd55c062f935f5e7b747404e5e13b718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2909"></a>Derleyici Hatası C2909
'tanımlayıcısı': işlev şablonunun açık örnekleme dönüş türü gerektirir  
  
 Bir açık örnekleme işlevi şablonu dönüş türüne açık belirtilmesini gerektiriyor. Örtük dönüş türü belirtimi çalışmaz.  
  
 Aşağıdaki örnek C2909 oluşturur:  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```