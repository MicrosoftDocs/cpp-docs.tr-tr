---
title: "Derleyici Hatası C3747 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3747
dev_langs: C++
helpviewer_keywords: C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32870584807d950dc6a1c2b6c9891f8190fad4dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3747"></a>Derleyici Hatası C3747
varsayılan tür parametresi eksik: parametre param  
  
 Genel veya şablon parametrelerini varsayılan değerlerle parametre listesinde varsayılan değerlere sahip parametrelerin izlenemiyor.  
  
 Aşağıdaki örnek C3747 oluşturur:  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 Olası çözüm:  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```