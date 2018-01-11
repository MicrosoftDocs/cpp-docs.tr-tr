---
title: "Derleyici Hatası C3161 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3161
dev_langs: C++
helpviewer_keywords: C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0cdbbd9364435ebcfad114331b6ba7289cb8010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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