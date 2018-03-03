---
title: "Derleyici Uyarısı (düzey 1) C4190 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 127eb4327826412d605f2a4a008e411880998073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4190"></a>Derleyici Uyarısı (düzey 1) C4190
'identifier1' C bağlantı belirtilen sahip, ancak UDT 'C ile uyumsuz olan identifier2' döndürür  
  
 Bir işlev veya işlev işaretçisi UDT (sınıfı, yapısı, numaralandırma veya birleşimi olan kullanıcı tanımlı tür,) dönüş türüne sahip ve `extern` "C" bağlantı. Bu yasal varsa:  
  
-   Bu işlev tüm çağrıları C++ içinden oluşur.  
  
-   C++'ta işlevi tanımıdır.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```