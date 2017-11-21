---
title: "Derleyici Hatası C2755 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2755
dev_langs: C++
helpviewer_keywords: C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56889ff193d057104c25b31bea8029e9426a9bbc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2755"></a>Derleyici Hatası C2755
'param': Kısmi uzmanlığı olmayan tür parametresi, basit bir tanımlayıcı olmalıdır  
  
 Tür olmayan parametresi bir basit bir tanımlayıcı, şey derleyici tek bir tanımlayıcı veya sabit bir değer derleme zamanında çözülebilir olması gerekir.  
  
 Aşağıdaki örnek C2755 oluşturur:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```