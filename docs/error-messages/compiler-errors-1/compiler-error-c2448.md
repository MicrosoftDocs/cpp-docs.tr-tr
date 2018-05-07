---
title: Derleyici Hatası C2448 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc62d7aeba0a128c9b736586e6c1502227de717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2448"></a>Derleyici Hatası C2448
'tanımlayıcısı': işlevi stili Başlatıcı işlev tanımı görünüyor  
  
 İşlev tanımı geçersiz.  
  
 Eski Tarz C dili resmi bazında bu hataya neden olabilir.  
  
 Aşağıdaki örnek C2448 oluşturur:  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```