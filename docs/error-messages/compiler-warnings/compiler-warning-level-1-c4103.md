---
title: "Derleyici Uyarısı (düzey 1) C4103 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4103
dev_langs: C++
helpviewer_keywords: C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 115c88a43f38065541fe925b023d61679c06be53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4103"></a>Derleyici Uyarısı (düzey 1) C4103
'filename': üstbilgisi de dahil olmak sonra değiştirilen hizalama #pragma pack(pop) eksik nedeniyle olabilir  
  
 Paket sınıfları düzenini etkiler ve yaygın olarak, üstbilgi dosyalardaki değişiklikler paketleme, olabilir sorunları.  
  
 #Pragma kullanmak [paketi](../../preprocessor/pack.md)bu uyarıyı çözümlemek için üstbilgi dosyası çıkmadan önce (pop).  
  
 Aşağıdaki örnek C4103 oluşturur:  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 Ardından,  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```