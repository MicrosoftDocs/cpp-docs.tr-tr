---
title: "Derleyici Hatası C3895 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3895
dev_langs: C++
helpviewer_keywords: C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75bd27d44ed74817cc23e6b58f036742d2d1979b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3895"></a>Derleyici Hatası C3895
'var': tür veri üyeleri 'geçici' olamaz  
  
 Veri üyeleri, örneğin belirli türdeki [değişmez değer](../../windows/literal-cpp-component-extensions.md) veya [initonly](../../dotnet/initonly-cpp-cli.md), olamaz [volatile](../../cpp/volatile-cpp.md).  
  
 Aşağıdaki örnek C3895 oluşturur:  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```