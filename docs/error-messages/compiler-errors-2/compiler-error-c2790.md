---
title: Derleyici Hatası C2790 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f1c90fed93666fad7513e2b4186a5baa2aa406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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