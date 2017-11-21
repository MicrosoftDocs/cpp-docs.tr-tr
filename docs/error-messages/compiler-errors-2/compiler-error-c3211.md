---
title: "Derleyici Hatası C3211 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3211
dev_langs: C++
helpviewer_keywords: C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f308f3a0be65175a62c53e3dd395b2e3b2984a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3211"></a>Derleyici Hatası C3211
'açık uzmanlık': açık uzmanlık kısmi uzmanlığı sözdizimini kullanarak, şablon <> kullanın  
  
 Bir açık uzmanlık ill oluşturulmuş.  
  
 Aşağıdaki örnek C3211 oluşturur:  
  
```  
// C3211.cpp  
// compile with: /LD  
template<class T>  
struct s;  
  
template<class T>  
// use the following line instead  
// template<>  
struct s<int>{};   // C3211  
```