---
title: "Derleyici Hatası C2489 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2489
dev_langs: C++
helpviewer_keywords: C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 697f64be4ee5ef0b38af6d8a027b9032f38d3db6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2489"></a>Derleyici Hatası C2489
'tanımlayıcısı': 'naked' işlevinde işlevi kapsamında izin verilmiyor otomatik veya kayıt değişkeni başlatıldı  
  
 Daha fazla bilgi için bkz: [naked](../../cpp/naked-cpp.md).  
  
 Aşağıdaki örnek C2489 oluşturur:  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```