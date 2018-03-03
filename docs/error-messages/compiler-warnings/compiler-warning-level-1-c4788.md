---
title: "Derleyici Uyarısı (düzey 1) C4788 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>Derleyici Uyarısı (düzey 1) C4788
'tanımlayıcısı': tanımlayıcısı 'numara' karakter kesildi  
  
 Derleyici bir işlev adı için izin verilen uzunluk sınırını kısıtlar. Derleyici funclets EH/SEH kodu oluşturduğunda, bazı metinleri işlevi adıyla eklenerek funclet adı oluşturur, örneğin "__catch", "\__unwind", veya başka bir dize.  
  
 Sonuçta elde edilen funclet adı çok uzun olabilir ve derleyici kesme ve C4788 oluşturur.  
  
 Bu uyarıyı çözmek için özgün işlevi adını kısaltın. İşlevi C++ şablonu işlev veya yöntem ise, bir typedef adının bir kısmını için kullanın. Örneğin:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 tarafından değiştirilebilir:  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Bu uyarı yalnızca oluşan [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyici.