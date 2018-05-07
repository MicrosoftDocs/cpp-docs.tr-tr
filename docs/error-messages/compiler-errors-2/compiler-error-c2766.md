---
title: Derleyici Hatası C2766 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2766
dev_langs:
- C++
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd83bc18e30fb9b183e27597b1c5902f734c88a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2766"></a>Derleyici Hatası C2766
Açık uzmanlık; 'uzmanlık' zaten tanımlandı  
  
 Yinelenen açık özelleştirmeleri izin verilmiyor. Daha fazla bilgi için bkz: [açık uzmanlık, işlev şablonları](../../cpp/explicit-specialization-of-function-templates.md).  
  
 Aşağıdaki örnek C2766 oluşturur:  
  
```  
// C2766.cpp  
// compile with: /c  
template<class T>   
struct A {};  
  
template<>   
struct A<int> {};  
  
template<>   
struct A<int> {};   // C2766  
// try the following line instead  
// struct A<char> {};  
```