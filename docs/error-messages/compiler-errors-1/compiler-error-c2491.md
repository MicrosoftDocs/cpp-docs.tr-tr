---
title: "Derleyici Hatası C2491 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2491
dev_langs: C++
helpviewer_keywords: C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 83b369d72b4d2ed296f6abeb68cc69b8c233326e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2491"></a>Derleyici Hatası C2491
'tanımlayıcısı': izin dllimport işlevinin tanımı  
  
 Olarak veri, statik veri üyeleri ve işlevleri bildirilebilir `dllimport`s ancak olarak tanımlanmamış `dllimport`s.  
  
 Bu sorunu gidermek için kaldırın `__declspec(dllimport)` işlevinin tanımından tanımlayıcısı.  
  
 Aşağıdaki örnek C2491 oluşturur:  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```