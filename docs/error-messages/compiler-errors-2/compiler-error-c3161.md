---
title: Derleyici Hatası C3161 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2d7aff3eb41c03f5be774704922340ac54126fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3161"></a>Derleyici Hatası C3161
'arabirimi': sınıf iç içe geçme, yapısı, UNION veya arabirim arabiriminde; geçersiz iç içe bir sınıf, yapı veya birleşim arabiriminde geçersiz  
  
 Bir [__interface](../../cpp/interface.md) yalnızca genel kapsamlı veya bir ad alanı içinde yer alabilir. Bir sınıf, yapı veya birleşim arabirimdeki yer alamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3161 oluşturur.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```