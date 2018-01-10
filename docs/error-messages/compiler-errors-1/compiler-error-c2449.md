---
title: "Derleyici Hatası C2449 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2449
dev_langs: C++
helpviewer_keywords: C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2736462f86446ada205d43afdbde63374e689254
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2449"></a>Derleyici Hatası C2449
bulunan ' {' dosyası kapsamındaki (işlev üstbilgisi eksik?)  
  
 Bir açma ayracı dosya kapsamda oluşur.  
  
 Bu hata noktalı işlevi üstbilgisi ile açılan parantez işlev tanımının arasına neden olabilir.  
  
 Aşağıdaki örnek C2499 oluşturur:  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```