---
title: Derleyici Uyarısı C4867 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b46bf4866791ec82ac5984132903e22ab16e07ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270891"
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