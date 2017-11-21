---
title: "Nasıl yapılır: yerel türlerde işleyicileri bildirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords: gcroot
dev_langs: C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b7507a0c941fa651f55fdf462b9d832cfd929632
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-declare-handles-in-native-types"></a>Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme
Yerel tür içinde tanıtıcı türü bildiremezsiniz. Vcclr.h sağlar tür kullanımı uyumlu sarmalayıcı şablonunu `gcroot` C++ yığınından CLR nesnesine başvurmak için. Bu şablon, sanal bir işleyiciyi yerel tür katıştırmak ve temel alınan tür değilmiş gibi davran sağlar. Çoğu durumda, kullandığınız `gcroot` nesnesi herhangi bir atama olmadan katıştırılmış tür olarak. Bununla birlikte, [her biri için de](../dotnet/for-each-in.md), kullanmak zorunda `static_cast` temeldeki yönetilen başvuruyu almak için.  
  
 `gcroot` Şablonu, atık toplanan yığına değer sınıfı "tanıtıcıları" sağlayan System::Runtime tesis kullanılarak gerçekleştirilir. İşleyicilerin kendileri toplanacak olmadığına dikkat edin ve artık kullanılmadığı zaman içinde yıkıcı tarafından kurtulurlar `gcroot` (Bu yıkıcı el ile çağrılamaz) sınıfı. Örneği varsa bir `gcroot` nesnesi yerel yığında çağırmanız gerekir, bu kaynağa silin.  
  
 Çalışma zamanı işleyici ile başvurduğu CLR nesnesi arasında bir ilişki korur. CLR nesnesi atık olarak toplanmış yığınla geçtiğinde, tanıtıcı nesnenin yeni adresini döndürür. Bir değişken atandığı önce sabitlenmiş olmak zorunda değildir bir `gcroot` şablonu.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl oluşturulacağını gösterir bir `gcroot` yerel yığında nesnesi.  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl oluşturulacağını gösterir bir `gcroot` yerel yığında nesnesi.  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl kullanılacağını göstermektedir `gcroot` kullanarak yerel tür içinde değer türleri (başvuru türleri değil) başvuruları tutmak için `gcroot` paketlenmiş türü.  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)