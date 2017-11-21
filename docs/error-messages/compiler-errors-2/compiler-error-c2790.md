---
title: "Derleyici Hatası C2790 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2790
dev_langs: C++
helpviewer_keywords: C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 11ea7285d20808f16f2588d50caebe99429c8da0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2790"></a>Derleyici Hatası C2790
'Süper': Bu anahtar sözcüğü yalnızca sınıf üye işlevi gövdesi içinde kullanılabilir  
  
 Bu hata iletisi görüntüleniyor kullanıcı herhangi bir zamanda çalışırsa kullanan anahtar sözcüğü [Süper](../../cpp/super.md) üye işlevi bağlamı dışında.  
  
 Aşağıdaki örnek C2790 oluşturur:  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```