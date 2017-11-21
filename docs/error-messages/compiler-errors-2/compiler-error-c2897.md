---
title: "Derleyici Hatası C2897 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2897
dev_langs: C++
helpviewer_keywords: C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d3aa9ae6c79d3320104d9689f82b894cf2b76d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2897"></a>Derleyici Hatası C2897
yok Edicisi/Sonlandırıcı işlevi şablonu olamaz  
  
 Bir yıkıcı (yıkıcı bir dizi tanımlarsınız) bir şablon bildirme izin için Yıkıcılar veya sonlandırıcılar, aşırı yüklenemez.  
  
 Aşağıdaki örnek C2897 oluşturur:  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2897 oluşturur.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2897 oluşturur.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```