---
title: "Derleyici Hatası C2084 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf9e0888e0f959d77198efe036c0234c985ea365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2084"></a>Derleyici Hatası C2084
İşlev '*işlevi*' gövde zaten var  
  
 İşlevi zaten tanımlanmış.  
  
 Visual Studio 2002 önce Visual C++ sürümlerinde  
  
-   Ek tanımları hiçbir zaman kullanılabilir olsa da derleyici aynı gerçek türe çözümlenmiş birden çok şablon özelleştirmeleri kabul eder. Derleyici şimdi bu birden çok tanımları algılar.  
  
-   `__int32`ve `int` ayrı türleri olarak kabul. Derleyici şimdi değerlendirir `__int32` eşanlamlısı olarak `int`. Bu işlev hem aşırı yüklüyse derleyici birden fazla tanımı algılar anlamına gelir `__int32` ve `int` ve bir hata verir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2084 oluşturur:  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
Bu hatayı düzeltmek için yinelenen tanımı kaldırın:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```