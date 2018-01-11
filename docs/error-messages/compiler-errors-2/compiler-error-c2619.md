---
title: "Derleyici Hatası C2619 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2619
dev_langs: C++
helpviewer_keywords: C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c39337ee76f015a4b7afa25ddd9176c6edb9501c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2619"></a>Derleyici Hatası C2619
'tanımlayıcısı': statik veri üyesi bir anonim yapı ya da UNION izin verilmiyor  
  
 Anonim yapı veya birleşim üyesi bildirilmiş `static`.  
  
 Aşağıdaki örnek C2619 oluşturur ve static anahtar sözcüğü kaldırarak düzeltmek gösterilmiştir.  
  
```  
// C2619.cpp  
int main() {  
   union { static int j; };  // C2619  
   union { int j; };  // OK  
}  
```