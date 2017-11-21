---
title: "Derleyici Hatası C2791 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2791
dev_langs: C++
helpviewer_keywords: C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 894f0fb735e4fea7d590eb53401243c0d8581c49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2791"></a>Derleyici Hatası C2791
Geçersiz 'Süper' kullanımı: 'sınıfı' tüm temel sınıflar yok  
  
 Anahtar sözcüğü [Süper](../../cpp/super.md) üye işlevi bir sınıfın tüm temel sınıflar yok bağlamında kullanıldı.  
  
 Aşağıdaki örnek C2791 oluşturur:  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```