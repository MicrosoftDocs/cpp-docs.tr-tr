---
title: "Önemli hata C1016 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1016
dev_langs: C++
helpviewer_keywords: C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ef8e1547b636ec6722daca3f73639d8e1db42d5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1016"></a>Önemli hata C1016
\##ifndef tanımlayıcı bir tanımlayıcı bekleniyor ıfdef bekleniyor  
  
 Koşullu derleme yönergesi ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) veya `#ifndef`) değerlendirmek için hiçbir tanımlayıcısı vardır. Hatayı gidermek için bir tanımlayıcı belirtin.  
  
 Aşağıdaki örnek C1016 oluşturur:  
  
```  
// C1016.cpp  
#ifdef   // C1016  
#define FC1016  
#endif  
  
int main() {}  
```  
  
 Olası çözüm:  
  
```  
// C1016b.cpp  
#ifdef X  
#define FC1016  
#endif  
  
int main() {}  
```