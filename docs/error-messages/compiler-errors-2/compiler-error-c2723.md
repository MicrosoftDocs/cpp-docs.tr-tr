---
title: "Derleyici Hatası C2723 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2723
dev_langs: C++
helpviewer_keywords: C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3816640569a503c8a56c4cf37f1bf23360b30a12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2723"></a>Derleyici Hatası C2723
'function': 'tanımlayıcısı' tanımlayıcısı işlev tanımı geçersiz  
  
 Belirleyici işlevi tanımlı bir sınıf bildiriminin dışında yer alamaz. `virtual` Belirleyicisi yalnızca bir üye işlevi bildirimi sınıf bildirimi içinde üzerinde belirtilebilir.  
  
 Aşağıdaki örnek C2723 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```