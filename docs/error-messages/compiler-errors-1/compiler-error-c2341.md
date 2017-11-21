---
title: "Derleyici Hatası C2341 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2341
dev_langs: C++
helpviewer_keywords: C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5460ff70c95fd593539a16140c52fa1490bffc4e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2341"></a>Derleyici Hatası C2341
'bölüm adı': segment #pragma data_seg, code_seg veya önceki bölümde kullanılacak kullanılarak tanımlanması gerekir  
  
 Bir [tahsis](../../cpp/allocate.md) henüz tarafından tanımlanan segmenti başvurduğu deyimi [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), veya [bölüm](../../preprocessor/section.md) pragmaları.  
  
 Aşağıdaki örnek C2341 oluşturur:  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 Olası çözüm:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```