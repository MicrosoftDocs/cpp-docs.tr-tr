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
ms.openlocfilehash: 2d3adf42ddb4df4365a45fd3ef24bccd682ac3c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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