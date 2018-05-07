---
title: Derleyici Hatası C3279 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a86f3dd637f84901559c4be8443a81425347237
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3279"></a>Derleyici Hatası C3279
sınıf şablonları de olarak açık işlemlerinden CLI ad alanında bildirilen kısmi ve açık özelleştirmeleri izin verilmiyor  
  
 `cli` Ad alanı Microsoft tarafından tanımlanır ve sahte şablonları içerir. Visual C++ derleyicisi kullanıcı tanımlı, kısmi ve açık özelleştirmeleri ve sınıf şablonlarının açık örneklemesi bu ad alanında izin vermiyor.  
  
 Aşağıdaki örnek C3279 oluşturur:  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```