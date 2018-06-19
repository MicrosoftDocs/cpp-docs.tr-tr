---
title: Derleyici Hatası C2755 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2755
dev_langs:
- C++
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a018554de91003b54ffc403f1527ca07f2d4a75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233542"
---
# <a name="compiler-error-c2755"></a>Derleyici Hatası C2755
'param': Kısmi uzmanlığı olmayan tür parametresi, basit bir tanımlayıcı olmalıdır  
  
 Tür olmayan parametresi bir basit bir tanımlayıcı, şey derleyici tek bir tanımlayıcı veya sabit bir değer derleme zamanında çözülebilir olması gerekir.  
  
 Aşağıdaki örnek C2755 oluşturur:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```