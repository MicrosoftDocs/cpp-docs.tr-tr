---
title: Derleyici Hatası C3065 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3065
dev_langs:
- C++
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7a6bb966fd973a9ede675e98761e8649ca20c27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3065"></a>Derleyici Hatası C3065
özellik bildirimi sınıfı olmayan kapsamında izin verilmiyor  
  
 [Özelliği](../../cpp/property-cpp.md) __declspec değiştiricisi sınıf dışında kullanıldı.  Bir özelliği yalnızca bir sınıf içinde bildirilebilir.  
  
 Aşağıdaki örnek C3065 oluşturur:  
  
```  
// C3065.cpp  
// compile with: /c  
__declspec(property(get=get_i)) int i;   // C3065  
  
class x {  
public:  
   __declspec(property(get=get_i)) int i;   // OK  
};  
```