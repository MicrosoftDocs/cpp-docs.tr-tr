---
title: Derleyici Hatası C2733 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc1857cd800dd2d395754b9ae95094d9f57aad27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2733"></a>Derleyici Hatası C2733
'izin işlevi' aşırı yüklenmiş işlevinin ikinci C bağlantı  
  
 Birden fazla aşırı yüklenmiş işlevi ile C bağlantı bildirildi. C bağlantı kullanırken, belirtilen işlevinin yalnızca bir form dış olabilir. Aşırı yüklenen işlevler ve ada sahip olduğundan, C programları ile kullanılamaz.  
  
 Aşağıdaki örnek C2733 oluşturur:  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```