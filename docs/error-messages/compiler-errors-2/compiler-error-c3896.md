---
title: Derleyici Hatası C3896 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc60c09d6fd99e56f0261409099e56713604a76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3896"></a>Derleyici Hatası C3896
'member': hatalı Başlatıcı: Bu değişmez değer veri üyesi 'ile nullptr' yalnızca ilk değer atanabilir  
  
 A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi başlatılmış yanlış.  Bkz: [nullptr](../../windows/nullptr-cpp-component-extensions.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C3896 oluşturur:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```