---
title: "Derleyici Hatası C3279 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3279
dev_langs: C++
helpviewer_keywords: C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 16bb13d226b6d4d5d5846f8302070bf0c9579cfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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