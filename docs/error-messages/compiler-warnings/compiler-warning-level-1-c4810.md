---
title: "Derleyici Uyarısı (düzey 1) C4810 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4810
dev_langs:
- C++
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 652aef44e86e1395ae9faa1d29d3ffe99473c76c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4810"></a>Derleyici Uyarısı (düzey 1) C4810
pragma pack(show) değerini n ==  
  
 Kullandığınızda bu uyarı **Göster** seçeneği [paketi](../../preprocessor/pack.md) pragması. *n*Geçerli paketi değeridir.  
  
 Örneğin, aşağıdaki kod C4810 uyarı paketi pragma ile nasıl çalıştığını gösterir:  
  
```  
// C4810.cpp  
// compile with: /W1 /LD  
// C4810 expected  
#pragma pack(show)  
#pragma pack(4)  
#pragma pack(show)  
```