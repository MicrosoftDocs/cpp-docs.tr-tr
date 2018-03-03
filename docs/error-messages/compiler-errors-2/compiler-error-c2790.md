---
title: "Derleyici Hatası C2790 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b10da64605743612a4d5522b5c19d1f2029ced8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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