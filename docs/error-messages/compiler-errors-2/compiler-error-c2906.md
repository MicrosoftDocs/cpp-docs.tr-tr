---
title: Derleyici Hatası C2906 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2906
dev_langs:
- C++
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08884f8a9304a2849d9bcbe13170d0bd38402a62
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243309"
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