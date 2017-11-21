---
title: "Derleyici Hatası C2953 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2953
dev_langs: C++
helpviewer_keywords: C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 147c5c837a40dd2a6b2507a576efe9046160e87c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2953"></a>Derleyici Hatası C2953
'tanımlayıcısı': sınıf şablonu zaten tanımlandı  
  
 Kaynak dosyayı denetleyin ve dosyaları diğer tanımlarını içerir.  
  
 Aşağıdaki örnek C2953 oluşturur:  
  
```  
// C2953.cpp  
// compile with: /c  
template <class T>  class A {};  
template <class T>  class A {};   // C2953  
template <class T>  class B {};   // OK  
```