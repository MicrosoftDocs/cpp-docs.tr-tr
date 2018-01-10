---
title: "Derleyici Hatası C2259 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2259
dev_langs: C++
helpviewer_keywords: C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bcb7b24bb39ba204653d2a99d6bc1d3e5d8142b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2259"></a>Derleyici Hatası C2259
'class': Özet sınıfın örneği oluşturulamıyor  
  
 Kod örneği bir Özet sınıf veya yapı bildirir.  
  
 Bir sınıf veya yapı işlevlerle bir veya daha fazla saf sanal örneği oluşturulamıyor. Türetilen bir sınıfın nesnelerini örneği oluşturmak için türetilmiş sınıf her saf sanal işlevi geçersiz kılmanız gerekir.  
  
 Daha fazla bilgi için bkz: [örtük olarak soyut sınıflar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 Aşağıdaki örnek C2259 oluşturur:  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 Arabirimden türetmek ve ortak dışında erişim izinlerine sahip bir türetilen sınıfta arabirim yöntemleri oluşturmak zaman C2259 alabilirsiniz.  Bu durum, genel erişim sağlamak için türetilmiş sınıf içinde uygulanan arabirim yöntemleri derleyici bekliyor kaynaklanır. Üye işlevleri daha kısıtlayıcı erişim izinleri olan bir arabirim için uyguladığınızda, derleyici bunları sırayla bir Özet sınıf türetilmiş sınıf kılan arabiriminde tanımlanan arabirim yöntemleri için uygulamaları olarak dikkate almaz.  
  
 Sorunun iki olası geçici çözümler vardır:  
  
-   Erişim izinleri için uygulanan yöntemleri ortak olun.  
  
-   Kapsam çözümü işleci arabirimi adı ile gerçekleştirilen yöntem adını nitelemek için türetilmiş sınıfta uygulanır arabirim yöntemleri için kullanın.  
  
 C2259 Visual C++ 2005'te yapıldığı uyumluluğu iş sonucunda da gerçekleşebilir **/ZC: wchar_t** artık varsayılan olarak açıktır. Bu durumda, C2599 ile ya da göre derleme çözümlenebilir **/Zc:wchar_t-**, önceki sürümlerden veya tercihen uyumlu olacak şekilde türlerinizi güncelleştirerek davranışı elde etmek üzere. Daha fazla bilgi için bkz: [/ZC: wchar_t (wchar_t yerel tür olan)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 Aşağıdaki örnek C2259 oluşturur:  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 Aşağıdaki örnek C2259 oluşturur:  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
