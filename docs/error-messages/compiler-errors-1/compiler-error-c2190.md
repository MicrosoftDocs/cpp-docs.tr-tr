---
title: Derleyici Hatası C2190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2190
dev_langs:
- C++
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8a40aa3ae2169233874ae806d65a63d1644283e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169874"
---
# <a name="compiler-error-c2190"></a>Derleyici Hatası C2190
İlk parametre listesi ikinci daha uzun  
  
 C işlev daha kısa bir parametre listesi ile ikinci kez bildirildi. C aşırı yüklenmiş işlevlerin desteklemez.  
  
 Aşağıdaki örnek C2190 oluşturur:  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```