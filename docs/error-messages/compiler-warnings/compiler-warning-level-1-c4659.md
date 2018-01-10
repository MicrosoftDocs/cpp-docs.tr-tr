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
ms.workload: cplusplus
ms.openlocfilehash: dd974c730a67489d9197b448f02a5042f77159f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4659"></a>Derleyici Uyarısı (düzey 1) C4659
\#pragma 'pragma': ayrılmış segment 'segmenti' kullanımını davranışı tanımlı olmayan, #pragma Açıklama (Bağlayıcı,...) kullanın  
  
 .Drectve seçeneği bağlayıcı için bir seçenek geçirmek için kullanıldı. Bunun yerine pragma kullanın [açıklama](../../preprocessor/comment-c-cpp.md) bağlayıcı seçeneği geçirme için.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```