---
title: "Derleyici Hatası C2943 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2943
dev_langs: C++
helpviewer_keywords: C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bbd2a3310bb3f5cd18c241f9923d051acde58eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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