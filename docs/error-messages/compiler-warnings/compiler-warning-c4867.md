---
title: "Derleyici Uyarısı C4867 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4867
dev_langs: C++
helpviewer_keywords: C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a412080d05e570711fcc65926459f9d2fcc45ed3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4867"></a>Derleyici Uyarısı C4867
'function': bağımsız değişken listesi; eksik işlev çağrısı 'çağrı' üyesi için bir işaretçi oluşturmak için kullanın  
  
 Üye işlev işaretçisi yanlış başlatıldı.  
  
 Bu uyarı için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: Gelişmiş işaretçi-üye uygunluk.  Visual C++ 2005 önce derlenmiş kod artık C4867 oluşturur.  
  
 Bu uyarı, hata olarak her zaman görüntülenir. Kullanım [uyarı](../../preprocessor/warning.md) bu uyarıyı devre dışı bırakmak için pragması. C4867 ve MFC/ATL hakkında daha fazla bilgi için bkz: [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4867 oluşturur.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```