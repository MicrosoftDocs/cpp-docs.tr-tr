---
title: korumalı (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68cf69cd0c14d56c75a2c67d4369264e7a2ee440
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406178"
---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>Sözdizimi  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Korumalı** anahtar sözcüğü belirtir sınıf üyelerine erişimi *üye listesi* kadar sonraki erişim belirticisi (**genel** veya **özel**) veya sınıf tanımının son. Olarak bildirilen sınıf üyeleri **korumalı** yalnızca aşağıdakiler tarafından kullanılabilir:  
  
-   Başlangıçta bu üyeleri bildiren sınıfın üye işlevleri.  
  
-   Başlangıçta bu üyeleri bildirilen sınıf arkadaşları.  
  
-   Başlangıçta bu üyeleri bildiren sınıftan genel veya korumalı erişimle türetilmiş sınıflar.  
  
-   Korumalı üyelere özel erişimi de olan, doğrudan özel olarak türetilmiş sınıflar.  
  
 Bir temel sınıfın adından önce zaman **korumalı** anahtar sözcüğü, temel sınıfın genel ve korumalı üyelerinin kendi türetilmiş sınıfın korumalı üyeleri olduğunu belirtir.  
  
 Korumalı üyeler gibi özel olmayan **özel** yalnızca bildirildikleri ancak kadar genel de değildir bu sınıfın üyeleri tarafından erişilebilir olan üyelerin **genel** içinde erişilebilir üyeler herhangi bir işlev.  
  
 Korumalı olarak da bildirilen üyeler **statik** türetilmiş bir sınıfın tüm arkadaş veya üye işleve erişilebilir. Korumalı olarak bildirilmemiş olan üyelere **statik** arkadaşlar ve üye işlevleri türetilen bir sınıfta yalnızca bir işaretçi başvurusu veya türetilmiş sınıfın nesnesi aracılığıyla erişilebilir.  
  
 İlgili bilgiler için bkz. [arkadaş](../cpp/friend-cpp.md), [genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md)ve üye erişimi tablosu [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>/clr Özel  
 CLR türlerinde, C++ erişim belirtici anahtar sözcükleri (**genel**, **özel**, ve **korumalı**) türler ve Derlemelerle yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [üye erişim denetimi](member-access-control-cpp.md).  
  
> [!NOTE]
>  İle derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.  
  
## <a name="end-clr-specific"></a>END /clr Özel  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)