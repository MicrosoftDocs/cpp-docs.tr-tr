---
title: Derleyici Hatası C2913 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2913
dev_langs:
- C++
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb587be189b83ba4804fd90440c98161fd5710a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245172"
---
# <a name="compiler-error-c2913"></a>Derleyici Hatası C2913
Açık uzmanlık; sınıf şablonu uzmanlaşması 'bildirimi' değil  
  
 Şablon olmayan sınıf specialize olamaz.  
  
 Aşağıdaki örnek C2913 oluşturur:  
  
```  
// C2913.cpp  
// compile with: /c  
class X{};  
template <class T> class Y{};  
  
template<> class X<int> {};   // C2913  
template<> class Y<int> {};  
```