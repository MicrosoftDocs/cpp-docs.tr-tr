---
title: "Temsilci (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs: C++
helpviewer_keywords: delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 43bab2679e958dbf8ffbd0f76b0d683636ba88de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="delegate--c-component-extensions"></a>temsilci (C++ Bileşen Uzantıları)
Bir işlev işaretçisi temsil eden bir tür bildirir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Windows çalışma zamanı ve ortak dil çalışma zamanı temsilciler destekler.  
  
### <a name="remarks"></a>Açıklamalar  
 `delegate`bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Bir tür bir delegate ise derleme zamanında algılamak için kullanmak `__is_delegate()` türü ayırdedici nitelik. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 C + +/ CX şu sözdizimiyle temsilciler destekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
access  
delegate  
return-type  
delegate-type-identifier  
(  
[ parameters ]  
)  
  
```  
  
### <a name="parameters"></a>Parametreler  
 *erişim*  
 (isteğe bağlı) Olabilir temsilci erişilebilirliğini `public` (varsayılan) veya `private`. İşlev prototipi ayrıca ile nitelendirilmesi `const` veya `volatile` anahtar sözcükler.  
  
 *dönüş türü*  
 İşlev prototipi dönüş türü.  
  
 *temsilci türü tanımlayıcısı*  
 Bildirilen temsilci türünün adı.  
  
 *parametreleri*  
 (İsteğe bağlı) Türleri ve işlev prototipi öğesinin tanımlayıcıları.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım *temsilci türü tanımlayıcısı* temsilci olarak aynı prototip sahip bir olay bildirmek için. Daha fazla bilgi için bkz: [temsilciler (C + +/ CX)](../cppcx/delegates-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Ortak dil çalışma zamanı şu sözdizimiyle temsilciler destekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
access  
delegate  
function_declaration  
  
```  
  
### <a name="parameters"></a>Parametreler  
 *erişim*  
 (isteğe bağlı) Derleme dışında temsilci erişilebilirliğini genel veya özel olabilir.  Varsayılan özeldir.  Bir sınıf içinde bir temsilci herhangi erişilebilirlik olabilir.  
  
 *function_declaration*  
 Temsilciye bağlı işlev imzası. Dönüş türü bir temsilci, herhangi bir yönetilen türü olabilir. Birlikte çalışabilirlik nedeniyle, bir temsilci dönüş türü bir CLS tür olması önerilir.  
  
 İlişkisiz bir temsilci, ilk parametreyi tanımlamak için *function_declaration* türünde olmalı `this` nesne işaretçisi. 
  
### <a name="remarks"></a>Açıklamalar  
 Çok noktaya yayın temsilcileri: "işlev işaretçisi" bir veya daha fazla yöntemlerine bir yönetilen sınıf içinde bağlanıp bağlanamayacağı. **Temsilci** anahtar sözcüğü bir çok noktaya yayın temsilci türü belirli yöntemi imzayla tanımlar.  
  
 Bir temsilci için bir statik yöntem gibi bir değer sınıfının bir yönteme de bağlı olabilir.  
  
 Bir temsilci aşağıdaki özelliklere sahiptir:  
  
-   Öğesinden devralınan **System::MulticastDelegate**.  
  
-   İki bağımsız değişken almayan bir kurucusunun: yönetilen bir sınıf için bir işaretçi veya **NULL** (durumunda, bir statik yöntem bağlama) ve tam bir yöntemi belirtilen türde.  
  
-   Adlı bir yönteme sahip `Invoke`, temsilci bildirilen imzası, imza eşleşir.  
  
 Bir temsilci çağrıldığında, kendi işlev vardı bağlı sırayla çağrılır.  
  
 Bir temsilci dönüş değeri, son eklenen üye işlevi dönüş değerdir.  
  
 Temsilciler aşırı yüklenemez.  
  
 Temsilciler bağlı veya kesildi.  
  
 İlişkili bir temsilci örneği olduğunda, ilk bağımsız değişken bir nesne başvurusu olacaktır.  Temsilci örneklemesi ikinci bağımsız değişkeni ya da bir değer türü yöntemi için bir yönetilen sınıf nesnesi ya da bir işaretçi bir yöntemini adresini olması gelecektir.   İkinci bağımsız değişkeni bir temsilci oluşturmada tam sınıfı kapsam sözdizimi ile yöntem adı ve address-of işleci uygulamak gerekir.  
  
 İlişkisiz bir temsilci örneği olduğunda, ilk bağımsız değişken ya da bir yönetilen sınıf nesnesi ya da bir değer türü yöntemi için bir işaretçi bir yöntemini adresi olacaktır.   Bağımsız değişken tam sınıfı kapsam sözdizimi ile yöntem adı ve address-of işleci uygulamak gerekir.  
  
 Statik veya genel işlevi için bir temsilci oluştururken, yalnızca bir parametresi gereklidir: işlevi (isteğe bağlı olarak, işlev adresi).  
  
 Temsilciler üzerinde daha fazla bilgi için bkz:  
  
-   [Nasıl yapılır: temsilcileri tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [Genel temsilciler (Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek, bildirme, başlatmak ve temsilciler çağırma gösterilmektedir.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **Çıktı**  
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)