---
title: Derleyici Hatası C3113 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3113
dev_langs:
- C++
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 220f400bd1ce80be039dcd8d572d20fad5da09f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245725"
---
# <a name="compiler-error-c3113"></a>Derleyici Hatası C3113
bir 'yapısı' şablon/genel olamaz  
  
 Sınıf şablonu veya sınıf dışında bir arabirim ya da bir enum genel yapılmaya çalışıldı.  
  
 Aşağıdaki örnek C3113 oluşturur:  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```