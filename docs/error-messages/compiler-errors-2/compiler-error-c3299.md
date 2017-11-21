---
title: "Derleyici Hatası C3299 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3299
dev_langs: C++
helpviewer_keywords: C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3612762f397914b6058516db7d8f56b840873c1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3299"></a>Derleyici Hatası C3299
'member_function': kısıtlamaları belirtemezsiniz temel yöntemden devralınan  
  
 Genel üye işlevi geçersiz kılarken kısıtlaması yan tümceleri (kısıtlamaları gelir kısıtlamaları devralınmaz yinelenen) belirtilemez.  
  
 Geçersiz kılma genel işlevi üzerinde kısıtlaması yan tümceleri devralınır.  
  
 Daha fazla bilgi için bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3299 oluşturur.  
  
```  
// C3299.cpp  
// compile with: /clr /c  
public ref struct R {  
   generic<class T>   
   where T : R  
   virtual void f();  
};  
  
public ref struct S : R {  
   generic<class T>   
   where T : R   // C3299  
   virtual void f() override;  
};  
```