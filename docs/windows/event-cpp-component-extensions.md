---
title: "Olay (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- event
- event_cpp
dev_langs: C++
helpviewer_keywords: event keyword [C++]
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e821d68fac0467d48a2056e1818c3fd58963581
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="event--c-component-extensions"></a>olay (C++ Bileşen Uzantıları)
`event` Anahtar sözcüğü bildiren bir *olay*, kayıtlı abonelere bildirim olduğu (*olay işleyicileri*) çeken bir şey gerçekleşen.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 C + +/ CX destekleyen bildirme bir *olay üye* veya bir *olay blok*. Bir olay üye bir olay bloğu bildirmek için toplu özelliktir. Varsayılan olarak, bir olay üye bildirir `add()`, `remove()`, ve `raise()` açıkça bir olay bloğunda bildirilen işlevleri. Bir olay üye işlevlerde özelleştirmek için bir olay bloğu bunun yerine bildirme ve ihtiyaç duyduğunuz işlevleri geçersiz kılar.  
  
 **Sözdizimi**  
  
```  
  
// event data member  
modifiereventdelegate^ event_name;     
  
// event block  
modifiereventdelegate^ event_name   
{  
   modifierreturn_valueadd(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **Parametreleri**  
  
 *Değiştirici*  
 Olay bildirimi ya da bir olay erişimci yöntemi kullanılabilir değiştiricisi.  Olası değerler şunlardır: `static` ve `virtual`.  
  
 *temsilci seçme*  
 [Temsilci](../windows/delegate-cpp-component-extensions.md), olay işleyicisi eşleşmelidir, imzası.  
  
 *EVENT_NAME*  
 Olayın adı.  
  
 *return_value*  
 Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir için dönüş türü olmalıdır `void`.  
  
 *parametreleri*  
 (isteğe bağlı) Parametrelerini `raise` imzası eşleşen yöntemi *temsilci* parametresi.  
  
 **Açıklamalar**  
  
 Bir olay bir temsilci için tetikleyen olayı yanıt verir ve imza ile uyumlu ve dönüş türü temeldeki temsilci yöntemlerini kaydetmek herhangi bir sınıftan istemcilerin üye işlevi (olay işleyicisi) arasındaki ilişkidir.  
  
 Olay bildirimleri iki tür vardır:  
  
 *olay veri üyesi*  
 Derleyici otomatik olarak depolama olayı için temsilci türünün bir üyesi biçiminde oluşturur ve iç oluşturur `add()`, `remove()`, ve `raise()` üye işlevleri. Bir olay veri üyesi bir sınıf içinde bildirilmelidir. Dönüş türü temsilci dönüş türü, olay işleyicisi dönüş türü eşleşmelidir.  
  
 *Olay bloğu*  
 Açıkça bildirme ve davranışını özelleştirmek bir olay bloğu sağlar `add()`, `remove()`, ve `raise()` yöntemleri.  
  
 Kullanabileceğiniz `operators+=` ve `operator-=` eklemek ve bir olayı kaldırmak için işleyici veya çağrı `add()` ve `remove()` yöntemleri açıkça.  
  
 `event`bağlama duyarlı bir anahtar sözcüktür; bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [olaylar (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx).  
  
 Ekleme ve bir olay işleyicisi kaldırmak istiyorsanız, ekleme işlemi tarafından döndürülen EventRegistrationToken yapısı kaydetmeniz gerekir. Sonra kaldırma işlemi, kaydedilen EventRegistrationToken yapısı kaldırılması için olay işleyicisini tanımlamak için kullanmanız gerekir.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 `event` Anahtar sözcüğü bir olay bildirme olanak sağlar. Bir olay bildirimleri bir şey olduğunda ilgi sağlamak bir sınıf için bir yol olur.  
  
 **Sözdizimi**  
  
```  
  
// event data member  
modifiereventdelegate^ event_name;   
  
// event block  
modifiereventdelegate^ event_name   
{  
   modifierreturn_valueadd(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **Parametreleri**  
  
 *Değiştirici*  
 Olay bildirimi ya da bir olay erişimci yöntemi kullanılabilir değiştiricisi.  Olası değerler şunlardır: `static` ve `virtual`.  
  
 *temsilci seçme*  
 [Temsilci](../windows/delegate-cpp-component-extensions.md), olay işleyicisi eşleşmelidir, imzası.  
  
 *EVENT_NAME*  
 Olayın adı.  
  
 *return_value*  
 Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir için dönüş türü olmalıdır `void`.  
  
 *parametreleri*  
 (isteğe bağlı) Parametrelerini `raise` imzası eşleşen yöntemi *temsilci* parametresi.  
  
 **Açıklamalar**  
  
 Bir olay bir temsilci için tetikleyen olayı yanıt verir ve imza ile uyumlu ve dönüş türü temeldeki temsilci yöntemlerini kaydetmek herhangi bir sınıftan istemcilerin üye işlevi (olay işleyicisi) arasındaki ilişkidir.  
  
 Temsilci kodunuzu olayın oluştuğunu gösteren zaman çağrılacağı bir veya daha fazla ilişkili yöntemleri olabilir. Bir program olayda .NET Framework ortak dil çalışma zamanı hedef diğer programlar için kullanılabilir hale getirilebilir.  
  
 Olay bildirimleri iki tür vardır:  
  
 *olay veri üyeleri*  
 Temsilci türünün bir üyesi biçiminde olayı için depolama, veri üyesi olayları derleyici tarafından oluşturulur.  Bir olay veri üyesi bir sınıf içinde bildirilmelidir. Bu olarak da bilinen önemsiz bir olaydır (aşağıdaki kod örneği bakın.)  
  
 *Olay blokları*  
 Olay blokları Ekle, Kaldır ve artırma yöntemleri uygulayarak Ekle, Kaldır ve raise yöntemlerinin davranışını özelleştirmenizi sağlar. Ekle, Kaldır ve raise yöntemlerinin imza temsilci imza eşleşmesi gerekir.  Olay blok olaylarını veri üyesi olmayan ve kullanım verileri üye olarak derleyici hatası oluşturur. 
  
 Olay işleyicisinin dönüş türü temsilci dönüş türü eşleşmelidir.  
  
 .NET Framework'teki bir yöntem değilmiş gibi bir veri üyesi davranabilirsiniz (diğer bir deyişle, `Invoke` karşılık gelen temsilci yöntemi). Yönetilen olay veri üyesi bildirmek için temsilci türü önceden gerekir. Buna karşılık, zaten tanımlanmazsa, bir yönetilen olay yöntemi karşılık gelen yönetilen temsilci örtük olarak tanımlar.  Kod örneği bir örnek için bu konunun sonundaki bakın.  
  
 Yönetilen bir olay bildirirken belirtebilirsiniz, olay işleyicileri eklendiğinde veya kaldırıldığında zaman çağrılacağı erişimciler ekleyip işleçleri += ve-= kullanma. Ekle, Kaldır ve raise yöntemleri açıkça çağrılabilir.  
  
 Oluşturmak ve olayları Visual c++'ta kullanmak için aşağıdaki adımlar izlenmelidir:  
  
1.  Oluşturun veya bir temsilci belirleyin. Kendi olay tanımlıyorsanız, ayrıca ile kullanmak üzere bir temsilci olduğundan emin olmalıdır `event` anahtar sözcüğü. Olay önceden tanımlanmış, .NET Framework Örneğin, ardından olay tüketicileri yalnızca adını temsilci bilmeniz.  
  
2.  İçeren bir sınıf oluşturun:  
  
    -   Temsilciden oluşturulan olay.  
  
    -   (isteğe bağlı) Temsilci örneği ile bildirilen doğrular bir yöntem `event` anahtar sözcüğü bulunmaktadır. Aksi takdirde, bu mantığı olay gönderir kodda yerleştirilmelidir.  
  
    -   Olay çağırma yöntemleri. Bu yöntemleri geçersiz kılmaları bazı temel sınıf işlevselliğinin olabilir.  
  
     Bu sınıf, olay tanımlar.  
  
3.  Yöntemleri bağlanma olayı için bir veya daha fazla sınıfları tanımlar. Bir veya daha fazla yöntemleri bu sınıfların her biri olay temel sınıf ile ilişkilendirin.  
  
4.  Olay kullanın:  
  
    -   Olay bildirimi içeren sınıfın bir nesnesi oluşturun.  
  
    -   Olay tanımını içeren sınıfın bir nesnesi oluşturun.  
  
 Daha fazla bilgi C + +/ CLI olayları, bkz:  
  
-   [Arabirimdeki olayları](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde Temsilciler, olayları ve olay işleyicileri bildiren çiftleri gösterilmektedir; (ekleme) abone olay işleyicileri; olay işleyicileri çağırma; ve ardından aboneliği (kaldırma) olay işleyicileri.  
  
```  
// mcppv2_events.cpp  
// compile with: /clr  
using namespace System;  
  
// declare delegates  
delegate void ClickEventHandler(int, double);  
delegate void DblClickEventHandler(String^);  
  
// class that defines events  
ref class EventSource {  
public:  
   event ClickEventHandler^ OnClick;   // declare the event OnClick  
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick  
  
   void FireEvents() {  
      // raises events  
      OnClick(7, 3.14159);  
      OnDblClick("Hello");  
   }  
};  
  
// class that defines methods that will called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
  
   void OnMyDblClick(String^ str) {  
      Console::WriteLine("OnDblClick: {0}", str);  
   }  
};  
  
int main() {  
   EventSource ^ MyEventSource = gcnew EventSource();  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
  
   // invoke events  
   MyEventSource->FireEvents();  
  
   // unhook handler to event  
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
}  
```  
  
 **Çıktı**  
  
```Output  
OnClick: 7, 3.14159  
  
OnDblClick: Hello  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği oluşturmak için kullanılan mantığı gösterir `raise` önemsiz bir olayın yöntemi: olay bir veya daha fazla üyeye sahipse, çağırma `raise` yöntemi örtük veya açık olarak temsilcisini çağırır. Temsilci dönüş türü değilse `void` ve sıfır olay aboneleri varsa `raise` yöntemi temsilci türü için varsayılan değeri döndürür. Hiçbir olay aboneleri varsa, çağırma `raise` yöntemi yalnızca döndürür ve hiçbir özel durum oluşturuldu. Temsilci türü döndürürse `void`, temsilci türü döndürdü.  
  
```  
// trivial_events.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int Del();  
public ref struct C {  
   int i;  
   event Del^ MyEvent;  
  
   void FireEvent() {  
      i = MyEvent();  
   }  
};  
  
ref struct EventReceiver {  
   int OnMyClick() { return 0; }  
};  
  
int main() {  
   C c;  
   c.i = 687;  
  
   c.FireEvent();  
   Console::WriteLine(c.i);  
   c.i = 688;  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);  
   Console::WriteLine(c.i);     
}  
```  
  
 **Çıktı**  
  
```Output  
0  
  
688  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)