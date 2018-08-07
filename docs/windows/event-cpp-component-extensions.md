---
title: Olay (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event
- event_cpp
dev_langs:
- C++
helpviewer_keywords:
- event keyword [C++]
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 107d721e4603fc1f22a5ff793a867b290472f10c
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570408"
---
# <a name="event--c-component-extensions"></a>olay (C++ Bileşen Uzantıları)
**Olay** anahtar sözcüğü bildiren bir *olay*, kayıtlı aboneleri için bir bildirim olduğu (*olay işleyicileri*), ilgilendiğiniz bir sorun oluştu.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 C + +/ CX destekler bildirme bir *olay üyesi* veya *olay blok*. Bir olay üyesi bir olay bloğu bildirmek için toplu özelliktir. Varsayılan olarak, bir olay üyesi bildirir `add()`, `remove()`, ve `raise()` açıkça bir olay blokta bildirilen işlevler. Bir olay üyesi işlevleri özelleştirmek için bir olay bloğu yerine bildirme ve ihtiyacınız olan işlevleri geçersiz kılın.  
  
 **Söz dizimi**  
  
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
  
 **Parametreler**  
  
 *Değiştiricisi*  
 Olay bildirimi ya da bir olay erişimci yöntemi kullanılabilir değiştiricisi.  Olası değerler **statik** ve **sanal**.  
  
 *delegate*  
 [Temsilci](../windows/delegate-cpp-component-extensions.md), imzası olan olay işleyicisi eşleşmesi gerekir.  
  
 *EVENT_NAME*  
 Olayın adı.  
  
 *return_value*  
 Olay erişimci yöntemi dönüş değeri.  Doğrulanabilir için dönüş türü olmalıdır **void**.  
  
 *Parametreleri*  
 (isteğe bağlı) Parametreler için `raise` imzası eşleşen yöntemi *temsilci* parametresi.  
  
 **Açıklamalar**  
  
 Bir olay bir temsilci olayı harekete yanıt verir ve imza ile uyumlu ve dönüş türü temel temsilci yöntemleri kaydetmek, istemcilerin herhangi bir sınıftan bir üye işlevi (olay işleyicisi) arasındaki ilişkidir.  
  
 Olay bildirimleri iki tür vardır:  
  
 *olay veri üyesi*  
 Derleyicinin otomatik olarak depolama olayı için temsilci türünün üyesi biçiminde oluşturur ve iç oluşturur `add()`, `remove()`, ve `raise()` üye işlevleri. Bir olay veri üyesi bir sınıf içinde bildirilmesi gerekir. Dönüş türünü temsilcinin dönüş türünü dönüş türü olay işleyicisinin eşleşmesi gerekir.  
  
 *Olay bloğu*  
 Açıkça bildirmek ve davranışını özelleştirmek bir olay bloğu sağlar `add()`, `remove()`, ve `raise()` yöntemleri.  
  
 Kullanabileceğiniz **işleçleri +=** ve **-= işleci** ekleme ve kaldırma olay işleyicisi veya çağrı `add()` ve `remove()` yöntemleri açıkça.  
  
 **olay** bir bağlama duyarlı anahtar sözcük; bkz [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [olaylar (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx).  
  
 Ekle ve Kaldır'ı bir olay işleyicisi yapmak istiyorsanız, ekleme işlemi tarafından döndürülen EventRegistrationToken yapısı kaydetmeniz gerekir. Ardından kaldırma işleminde kaldırılacak olay işleyicisi tanımlamak için kaydedilen EventRegistrationToken yapısı kullanmalısınız.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Olay** anahtar sözcüğü, bir olay bildirin olanak sağlar. Olay bildirimleri şeyler olduğunda ilgi sağlamak bir sınıf için bir yol olur.  
  
 **Söz dizimi**  
  
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
  
 **Parametreler**  
  
 *Değiştiricisi*  
 Olay bildirimi ya da bir olay erişimci yöntemi kullanılabilir değiştiricisi.  Olası değerler **statik** ve **sanal**.  
  
 *delegate*  
 [Temsilci](../windows/delegate-cpp-component-extensions.md), imzası olan olay işleyicisi eşleşmesi gerekir.  
  
 *EVENT_NAME*  
 Olayın adı.  
  
 *return_value*  
 Olay erişimci yöntemi dönüş değeri.  Doğrulanabilir için dönüş türü olmalıdır **void**.  
  
 *Parametreleri*  
 (isteğe bağlı) Parametreler için `raise` imzası eşleşen yöntemi *temsilci* parametresi.  
  
 **Açıklamalar**  
  
 Bir olay bir temsilci olayı harekete yanıt verir ve imza ile uyumlu ve dönüş türü temel temsilci yöntemleri kaydetmek, istemcilerin herhangi bir sınıftan bir üye işlevi (olay işleyicisi) arasındaki ilişkidir.  
  
 Temsilci, kodunuzu olayın oluştuğunu gösteriyorsa, çağrılacak bir veya daha fazla ilişkili yöntemi olabilir. Bir programda bir olay .NET Framework ortak dil çalışma zamanını hedefleyen diğer programlar için kullanılabilir hale getirilebilir.  
  
 Olay bildirimleri iki tür vardır:  
  
 *olay veri üyesi*  
 Temsilci türünün üyesi biçiminde bir olay için depolama, veri üyesi olayları için derleyici tarafından oluşturulur.  Bir olay veri üyesi bir sınıf içinde bildirilmesi gerekir. Önemsiz bir olay olarak da bilinen budur (aşağıdaki kod örneğine bakın.)  
  
 *Olay blokları*  
 Olay blokları Ekle, remove ve raise yöntemleri uygulayarak Ekle, remove ve raise yöntemleri davranışını özelleştirmenizi sağlar. İmza Ekle, Kaldır ve raise yöntemlerinin temsilcisinin imzasıyla eşleşmelidir.  Olay bloğu olaylar veri üyesi olmayan ve herhangi bir kullanımından veri üyesi olarak bir derleme hatasına neden olur. 
  
 Olay işleyicisi dönüş türünü temsilcinin dönüş türü eşleşmelidir.  
  
 .NET Framework, bir yöntemi gibi bir veri üyesi davranabilir (diğer bir deyişle, `Invoke` , karşılık gelen bir temsilci yöntemi). Yönetilen bir olay veri üyesi bildirmek için temsilci türüyle önceden gerekir. Buna karşılık, yönetilen bir olay yöntemi, örtük olarak zaten tanımlı değilse karşılık gelen yönetilen temsilci tanımlar.  Bir örnek için bu konunun sonunda kod örneğine bakın.  
  
 Yönetilen bir olay bildirirken belirtebileceğiniz ekleme ve kaldırma olay işleyicileri eklendiğinde veya kaldırıldığında çağrılır erişimcileri işleçleri += ve-= kullanarak. Add, remove ve raise yöntemi açıkça çağrılabilir.  
  
 Oluşturma ve olayları Visual c++'ta kullanmak için aşağıdaki adımlar atılmalıdır:  
  
1.  Oluşturma veya bir temsilci tanımlama. Kendi olay tanımlıyorsanız, ayrıca bir temsilci ile kullanılacak olduğunu emin olmanız gerekir **olay** anahtar sözcüğü. Olay önceden tanımlanmış, .NET Framework Örneğin, ardından olay tüketicilerinin yalnızca adını temsilci bilmeniz.  
  
2.  İçeren bir sınıf oluşturun:  
  
    -   Bir olay temsilcisi oluşturuldu.  
  
    -   (isteğe bağlı) Temsilci örneği ile bildirilen doğrulayan bir yöntem **olay** anahtar sözcüğü bulunmaktadır. Aksi takdirde, bu mantık, olayı tetikler kodda yerleştirilmelidir.  
  
    -   Olayı çağıran yöntemleri. Bu yöntemler, bazı temel sınıf işlevselliğini geçersiz kılmalarına olabilir.  
  
     Bu sınıf, olayı tanımlar.  
  
3.  Yöntemleri connect etkinliği için bir veya daha fazla sınıflar tanımlayın. Bu sınıfların her birini bir veya daha fazla yöntemi temel sınıf içinde olay ile ilişkilendireceksiniz.  
  
4.  Olay kullanın:  
  
    -   Olay bildirimi içeren sınıfın bir nesnesi oluşturun.  
  
    -   Olay tanımını içeren sınıfın bir nesnesi oluşturun.  
  
 Daha fazla bilgi C + +/ CLI olaylara bakın  
  
-   [Arabirim içindeki olaylar](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneği, bildirim çiftlerini Temsilciler, olayları ve olay işleyicileri gösterilmektedir; (eklemek) abone; olay işleyicileri olay işleyicilerini çağırma; ve ardından aboneliği (kaldırma) olay işleyicileri.  
  
```cpp  
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
  
 **Output**  
  
```Output  
OnClick: 7, 3.14159  
  
OnDblClick: Hello  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği oluşturmak için kullanılan mantıksal gösterir `raise` önemsiz bir olayın yöntemi: olay bir veya daha fazla üyeye sahipse, çağırma `raise` yöntemini açıkça veya örtük olarak temsilci çağırır. Temsilcinin dönüş türü değilse **void** ve sıfır etkinlik abonelerinden varsa `raise` yöntemi temsilci türü için varsayılan değeri döndürür. Hiçbir etkinlik abonelerinden varsa, çağırma `raise` yöntemi yalnızca döndürür ve hiçbir özel durum oluşturulur. Temsilci türü değil dönerseniz **void**, temsilci türü döndürülür.  
  
```cpp  
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
  
 **Output**  
  
```Output  
0  
  
688  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)