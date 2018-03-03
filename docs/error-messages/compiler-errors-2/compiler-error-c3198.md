---
title: "Derleyici Hatası C3198 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3198
dev_langs:
- C++
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0a82564b8c2f9e8ba785cb54dd66895c5772d3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3198"></a>Derleyici Hatası C3198
kayan nokta pragmaları geçersiz kullanımı: fenv_access pragması yalnızca kesin modunda çalışır  
  
 [fenv_access](../../preprocessor/fenv-access.md) pragma altında kullanıldı bir [/fp](../../build/reference/fp-specify-floating-point-behavior.md) dışında ayarı **/fp: kesin**.  
  
 Aşağıdaki örnek C3198 oluşturur:  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```