---
title: "Derleyici Hatası C2081 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2081
dev_langs: C++
helpviewer_keywords: C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20f9f98ca03b9ed71d360b1b7c8bb64494a58416
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2081"></a>Derleyici Hatası C2081
'tanımlayıcısı': biçimsel parametresi listesi geçersiz ad  
  
 Tanımlayıcı Sözdizimi hatası neden oldu.  
  
 Bu hata için biçimsel parametresi listesi eski stili kullanılarak neden olabilir. Biçimsel parametresi listesinde biçimsel parametresi türünü belirtmeniz gerekir.  
  
 Aşağıdaki örnek C2081 oluşturur:  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Olası çözüm:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```