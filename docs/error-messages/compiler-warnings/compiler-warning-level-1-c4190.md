---
title: Derleyici Uyarısı (düzey 1) C4190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e62f6bcfaa499338d5fde1d09cb91574241ce8a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277900"
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