---
title: "korumalı (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: protected_cpp
dev_langs: C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02366a53f02142f66aa5dca493c5460c9f2d1d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>Sözdizimi  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `protected` Anahtar sözcüğü belirtir sınıf üyelerine erişimi *üye listesi* sonraki erişim belirticisi kadar (**ortak** veya `private`) veya sınıf tanımını sonuna. `protected` olarak bildirilen sınıf üyeleri yalnızca aşağıdakiler tarafından kullanılabilir:  
  
-   Başlangıçta bu üyeleri bildiren sınıfın üye işlevleri.  
  
-   Başlangıçta bu üyeleri bildirilen sınıf arkadaşları.  
  
-   Başlangıçta bu üyeleri bildiren sınıftan genel veya korumalı erişimle türetilmiş sınıflar.  
  
-   Korumalı üyelere özel erişimi de olan, doğrudan özel olarak türetilmiş sınıflar.  
  
 Bir temel sınıfın adından önce geldiği zaman, `protected` anahtar sözcüğü, temel sınıfın genel ve korumalı üyelerinin aynı zamanda kendi türetilmiş sınıfın korumalı üyeleri olduğunu belirtir.  
  
 Korumalı üye olarak özel olmayan `private` yalnızca bildirilen ancak olarak genel olarak olmadıkları sınıfı üyeleri erişilebilir üyeleri **ortak** herhangi bir işlevde erişilebilir üyeleri.  
  
 Korumalı olarak da bildirilen üyeler **statik** herhangi türetilmiş bir sınıf arkadaş veya üye işlevine erişilebilir. Korumalı olarak bildirilmemiş üyeler **statik** arkadaşlarınıza ve üye işlevleri yalnızca bir başvuru için işaretçi veya türetilmiş bir sınıf nesnesinin üzerinden türetilmiş bir sınıf içinde erişilebilir.  
  
 İlgili bilgi için bkz: [arkadaş](../cpp/friend-cpp.md), [ortak](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md)ve üye erişimi tabloda [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>/clr Özel  
 CLR Türleri'nde, C++ erişim belirteci anahtar sözcükler (**ortak**, `private`, ve `protected`) türlerini ve derlemeleri açısından yöntemleri görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz: [üye erişim denetimi](member-access-control-cpp.md).  
  
> [!NOTE]
>  Derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranış tarafından etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.  
  
## <a name="end-clr-specific"></a>END /clr Özel  
  
## <a name="example"></a>Örnek  
  
```  
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)