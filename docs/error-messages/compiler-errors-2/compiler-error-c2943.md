---
title: Derleyici Hatası C2943 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2943
dev_langs:
- C++
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6009428a151ee9959766db6213d2447eaf836c2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242744"
---
# <a name="compiler-error-c2943"></a>Derleyici Hatası C2943
'class': türü sınıfı kimliği bir şablon bir tür bağımsız değişkeni olarak yeniden tanımlandı  
  
 Bir genel veya şablon tür bağımsız değişkeni olarak bir simge yerine, genel veya Şablon sınıfı kullanamazsınız.  
  
 Aşağıdaki örnek C2943 oluşturur:  
  
```  
// C2943.cpp  
// compile with: /c  
template<class T>  
class List {};  
  
template<class List<int> > class MyList;   // C2943  
template<class T >  class MyList;  
```