---
title: Derleyici Hatası C2491 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e46d63f6602af7fe962f8b139c93a4b9a561783
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198891"
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