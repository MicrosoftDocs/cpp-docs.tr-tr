---
title: Derleyici Hatası C2833 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff066510292690bc940f18ab8d63605eb8627308
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2833"></a>Derleyici Hatası C2833
'işleci işleci' tanınan işleci veya türü değil  
  
 Word `operator` geçersiz kılmak istediğiniz bir işleç veya dönüştürmek istediğiniz bir türü tarafından gelmelidir.  
  
 Yönetilen bir tür tanımlayabilirsiniz işleçleri listesi için bkz: [kullanıcı tanımlı işleçler](../../dotnet/user-defined-operators-cpp-cli.md).  
  
 Aşağıdaki örnek C2833 oluşturur:  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```