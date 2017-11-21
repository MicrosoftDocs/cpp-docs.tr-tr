---
title: "Derleyici Hatası C2646 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2646
dev_langs: C++
helpviewer_keywords: C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 353f65b4d9702ed82ff92eae63fcedaa6adba227
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2646"></a>Derleyici Hatası C2646
bir anonim yapısı veya genel adresindeki UNION veya ad alanı kapsamı statik bildirilmelidir  
  
 Anonim yapı ya da UNION genel olduğundan veya ad alanı kapsamına ancak bildirilen `static`.  
  
 Aşağıdaki örnek C2646 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```