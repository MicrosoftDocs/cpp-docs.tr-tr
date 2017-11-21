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
ms.openlocfilehash: f68363a0d3a6c5b9354f89993fd658cf227edd0f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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