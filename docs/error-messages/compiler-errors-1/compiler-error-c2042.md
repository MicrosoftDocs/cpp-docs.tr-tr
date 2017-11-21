---
title: "Derleyici Hatası C2042 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2042
dev_langs: C++
helpviewer_keywords: C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7907e4407e58e6c05a4c352d78d744d4226153dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2042"></a>Derleyici Hatası C2042
İmzalı ve imzasız anahtar sözcükleri birbirini dışlayan  
  
 Anahtar sözcükler `signed` ve `unsigned` tek bir bildirimde kullanılır.  
  
 Aşağıdaki örnek C2042 oluşturur:  
  
```  
// C2042.cpp  
unsigned signed int i;   // C2042  
```  
  
 Olası çözüm:  
  
```  
// C2042b.cpp  
// compile with: /c  
unsigned int i;  
signed int ii;  
```