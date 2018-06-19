---
title: Derleyici Hatası C2084 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce1510dd6e78b8774d3cc433f583c16cdbb8d06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33173883"
---
# <a name="compiler-error-c2084"></a>Derleyici Hatası C2084
İşlev '*işlevi*' gövde zaten var  
  
 İşlevi zaten tanımlanmış.  
  
 Visual Studio 2002 önce Visual C++ sürümlerinde  
  
-   Ek tanımları hiçbir zaman kullanılabilir olsa da derleyici aynı gerçek türe çözümlenmiş birden çok şablon özelleştirmeleri kabul eder. Derleyici şimdi bu birden çok tanımları algılar.  
  
-   `__int32` ve `int` ayrı türleri olarak kabul. Derleyici şimdi değerlendirir `__int32` eşanlamlısı olarak `int`. Bu işlev hem aşırı yüklüyse derleyici birden fazla tanımı algılar anlamına gelir `__int32` ve `int` ve bir hata verir.  
  
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