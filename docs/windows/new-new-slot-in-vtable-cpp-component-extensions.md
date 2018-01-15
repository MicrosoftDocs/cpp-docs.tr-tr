---
title: "Yeni (vtable'de yeni yuva) (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f208a62fd49e7aea67acf5b7e3e49d3571f8d910
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>yeni (vtable'da yeni yuva) (C++ Bileşen Uzantıları)
`new` Anahtar sözcüğü gösterir sanal üyesi vtable'de yeni yuva alırsınız.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Windows çalışma zamanı'nda desteklenmiyor.  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 İçinde bir **/CLR** derleme `new` sanal üyesi vtable'de yeni yuva alırsınız; işlevi bir temel sınıf yöntemi kılmaz gösterir.  
  
 `new`işlev için IL eklenecek newslot değiştiricisi neden olur.  Newslot hakkında daha fazla bilgi için bkz:  
  
-   [MethodInfo.GetBaseDefinition yöntemi](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [Hatalı MethodAttributes numaralandırması](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek etkisini gösterir `new`.  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Output**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)