---
title: "Derleyici Hatası C2491 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fec3aba1430849b68076328db8c1084a2bca3221
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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