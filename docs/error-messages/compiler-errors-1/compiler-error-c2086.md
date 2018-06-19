---
title: Derleyici Hatası C2086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f1a21c06adeeda5d9db428e984da51f06addb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170261"
---
# <a name="compiler-error-c2086"></a>Derleyici Hatası C2086
'tanımlayıcısı': yeniden tanımlama  
  
 Tanımlayıcısı birden çok kez tanımlı değil veya önceki bir sonraki bildirimi farklıdır.  
  
 C2086 de başvuruda bulunulan bir C# derleme için artımlı derleme sonucu olabilir. Bu hatayı gidermek için C# derleme yeniden oluşturun.  
  
 Aşağıdaki örnek C2086 oluşturur:  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```