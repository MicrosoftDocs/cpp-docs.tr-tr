---
title: "Derleyici Uyarısı (düzey 1) C4659 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4659
dev_langs: C++
helpviewer_keywords: C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abaef666a5553969ab1290118b8668c50c2bba3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4659"></a>Derleyici Uyarısı (düzey 1) C4659
\#pragma 'pragma': ayrılmış segment 'segmenti' kullanımını davranışı tanımlı olmayan, #pragma Açıklama (Bağlayıcı,...) kullanın  
  
 .Drectve seçeneği bağlayıcı için bir seçenek geçirmek için kullanıldı. Bunun yerine pragma kullanın [açıklama](../../preprocessor/comment-c-cpp.md) bağlayıcı seçeneği geçirme için.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```