---
title: "Derleyici Hatası C2480 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2480
dev_langs: C++
helpviewer_keywords: C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06f6c536d5756a19e28df7060373512e3e883a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2480"></a>Derleyici Hatası C2480
'tanımlayıcısı': 'iş parçacığı' statik kapsam veri öğeleri için geçerli değil yalnızca  
  
 Kullanamazsınız `thread` özniteliği bir otomatik değişkeni, statik olmayan veri üyesi, işlev parametresi veya işlev bildirimleri ya da tanımları.  
  
 Kullanım `thread` genel değişkenler, statik veri üyeleri ve yalnızca yerel statik değişkenler özniteliği.  
  
 Aşağıdaki örnek C2480 oluşturur:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```