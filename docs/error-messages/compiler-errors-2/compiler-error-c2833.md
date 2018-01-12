---
title: "Derleyici Hatası C2833 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2833
dev_langs: C++
helpviewer_keywords: C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 019fa3cb0b36d9062bc972b01d434afe6e3848aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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