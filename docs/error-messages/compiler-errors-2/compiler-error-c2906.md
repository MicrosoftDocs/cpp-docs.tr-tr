---
title: "Derleyici Hatası C2906 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2906
dev_langs: C++
helpviewer_keywords: C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: da2806a0a945533fcc90e0a3d1045ff4f3c3b766
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2906"></a>Derleyici Hatası C2906
'uzmanlık': açık uzmanlık 'şablon <>' gerektirir  
  
 Şablonlarının açık alt uzmanlaşması için yeni sözdizimini kullanmanız gerekir.  
  
 Aşağıdaki örnek C2906 oluşturur:  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```