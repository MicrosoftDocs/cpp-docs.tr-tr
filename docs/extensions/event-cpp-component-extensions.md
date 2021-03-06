---
title: Event anahtar sözcüğü (C++/CLı ve C++/CX)
description: Microsoft C++ Bileşen Uzantıları anahtar sözcüğünü kullanmayı öğrenin `event` .
ms.date: 11/20/2020
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.openlocfilehash: 6a2fa97140f747b4afc380b57f8f7c71f08875db
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483249"
---
# <a name="event-keyword-ccli-and-ccx"></a>`event` anahtar sözcüğü (C++/CLı ve C++/CX)

**`event`** Anahtar sözcüğü, ilgilendiğiniz abonelere (*olay işleyicileri*) bir sorun oluştuğunu bildiren bir *olay* bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

C++/CX, bir *olay üyesinin* veya bir *olay bloğunun* bildirimini destekler. Olay üyesi bir olay bloğunu bildirmek için toplu bir özelliktir. Varsayılan olarak, bir olay üyesi, `add` `remove` , ve `raise` bir olay bloğunda açıkça belirtilen işlevleri bildirir. Bir olay üyesinde işlevleri özelleştirmek için, bunun yerine bir olay bloğu bildirin ve ardından ihtiyacınız olan işlevleri geçersiz kılın.

### <a name="syntax"></a>Söz dizimi

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Parametreler

*icisi*\
Olay bildiriminde veya bir olay erişimci yönteminde kullanılabilen bir değiştirici.  Olası değerler şunlardır **`static`** **`virtual`** .

*ğini*\
İmza olay işleyicisinin eşleşmesi gereken [temsilci](delegate-cpp-component-extensions.md).

*event_name*\
Olayın adı.

*return_value*\
Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir olması için, dönüş türü olmalıdır **`void`** .

*parametrelere*\
seçim `raise` Metot için *temsilci* parametresinin imzasıyla eşleşen parametreler.

### <a name="remarks"></a>Açıklamalar

Bir olay, bir temsilci ve *olay işleyicisi* arasındaki ilişkidir. Olay işleyicisi, olay tetiklendiğinde yanıt veren bir üye işlevdir. Herhangi bir sınıftan istemcilerin, temsilcinin imzasıyla ve dönüş türüyle eşleşen yöntemleri kaydetmesi için izin verir.

İki tür olay bildirimi vardır:

*Olay veri üyesi*\
Derleyici, temsilci türünün bir üyesi olan olay için otomatik olarak depolama oluşturur ve iç `add` , `remove` ve `raise` üye işlevleri oluşturur. Bir olay veri üyesinin bir sınıf içinde bildirilmelidir olması gerekir. Temsilcinin dönüş türünün dönüş türü, olay işleyicisinin dönüş türü ile aynı olmalıdır.

*olay bloğu*\
Bir olay bloğu,, ve yöntemlerinin davranışını açık bir şekilde bildirmenize ve özelleştirmenize olanak sağlar `add` `remove` `raise` .

`operator +=` `operator -=` Bir olay işleyicisi eklemek ve kaldırmak ya da `add` ve yöntemlerini açıkça çağırmak için kullanabilirsiniz `remove` .

**`event`** bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Olaylar (C++/CX)](../cppcx/events-c-cx.md).

Bir olay işleyicisini eklemek ve daha sonra kaldırmak için, `EventRegistrationToken` işlem tarafından döndürülen yapıyı kaydedin `add` . Sonra işlem sırasında `remove` , `EventRegistrationToken` kaldırılacak olay işleyicisini belirlemek için kaydedilmiş yapıyı kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Event** anahtar sözcüğü bir olay bildirmenize olanak tanır. Bir olay, bir sınıfın bir şey olduğunda bildirim sağlaması için bir yoldur.

### <a name="syntax"></a>Söz dizimi

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Parametreler

*icisi*\
Olay bildiriminde veya bir olay erişimci yönteminde kullanılabilen bir değiştirici.  Olası değerler şunlardır **`static`** **`virtual`** .

*ğini*\
İmza olay işleyicisinin eşleşmesi gereken [temsilci](delegate-cpp-component-extensions.md).

*event_name*\
Olayın adı.

*return_value*\
Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir olması için, dönüş türü olmalıdır **`void`** .

*parametrelere*\
seçim `raise` Metot için *temsilci* parametresinin imzasıyla eşleşen parametreler.

### <a name="remarks"></a>Açıklamalar

Bir olay, bir temsilci ve *olay işleyicisi* arasındaki ilişkidir. Olay işleyicisi, olay tetiklendiğinde yanıt veren bir üye işlevdir. Herhangi bir sınıftan istemcilerin, temel temsilcinin imzasıyla ve dönüş türüyle eşleşen yöntemleri kaydettirmesine olanak tanır.

Temsilcinin bir veya daha fazla ilişkili yöntemi olabilir. Bu yöntemler, kodunuzun olayın oluştuğunu gösterdiği zaman çağrılır. Bir programdaki bir olay, .NET Framework ortak dil çalışma zamanını hedefleyen diğer programlar için kullanılabilir hale getirilebilir.

İki tür olay bildirimi vardır:

*Olay veri üyeleri*\
Derleyici, veri üyesi olayları için temsilci türünün bir üyesi olarak depolama oluşturur. Bir olay veri üyesinin bir sınıf içinde bildirilmelidir olması gerekir. Bu, *Önemsiz bir olay* olarak da bilinir. Örnek için kod örneğine bakın.

*olay blokları*\
Olay blokları,, ve yöntemleri uygulayarak,, `add` `remove` ve yöntemlerinin davranışını `raise` özelleştirmenize `add` olanak sağlar `remove` `raise` . `add`, Ve yöntemlerinin imzası, `remove` `raise` temsilcinin imzasıyla aynı olmalıdır. Olay engelleme olayları veri üyesi değildir. Veri üyesi olarak herhangi bir kullanım derleyici hatası oluşturur.

Olay işleyicisinin dönüş türü, temsilcinin dönüş türüyle aynı olmalıdır.

.NET Framework, bir veri üyesini bir yöntemin kendisi (yani, `Invoke` karşılık gelen temsilcinin yöntemi) gibi kabul edebilirsiniz. Bunu yapmak için, yönetilen bir olay veri üyesini bildirmek üzere temsilci türünü önceden tanımlayın. Bunun aksine, yönetilen bir olay yöntemi zaten tanımlı değilse karşılık gelen yönetilen temsilciyi örtülü olarak tanımlar. Örnek için bu makalenin sonundaki kod örneğine bakın.

Yönetilen bir olay bildirirken, ve `add` `remove` işleçleri kullanılarak olay işleyicileri eklendiğinde veya kaldırıldığında çağrılacak erişimcileri belirtebilirsiniz **`+=`** **`-=`** . `add`, `remove` Ve `raise` yöntemleri açık bir şekilde çağrılabilir.

Aşağıdaki adımlar, Microsoft C++ ' da olay oluşturmak ve kullanmak için gerçekleştirilmelidir:

1. Bir temsilci oluşturun veya seçin. Kendi olaylarınızı tanımlıyorsanız, anahtar sözcüğüyle kullanmak için bir temsilci olduğundan da emin olmanız gerekir **`event`** . Olay önceden öntanımlı ise, .NET Framework Örneğin, olay tüketicilerinin yalnızca temsilcinin adını bilmeleri gerekir.

2. Şunu içeren bir sınıf oluşturun:

   - Temsilciden oluşturulan bir olay.

   - Seçim Anahtar sözcükle belirtilen temsilcinin bir örneğinin var olduğunu doğrulayan bir yöntem **`event`** . Aksi takdirde, bu mantık olayını harekete uygulayan koda yerleştirilmelidir.

   - Olayı çağıran Yöntemler. Bu yöntemler bazı temel sınıf işlevlerinin geçersiz kılmaları olabilir.

   Bu sınıf, olayı tanımlar.

3. Olayları olaya bağlayan bir veya daha fazla sınıf tanımlayın. Bu sınıfların her biri, temel sınıftaki olayla bir veya daha fazla yöntemi ilişkilendirir.

4. Olayı kullanın:

   - Olay bildirimini içeren sınıfın bir nesnesini oluşturun.

   - Olay tanımını içeren sınıfın bir nesnesini oluşturun.

C++/CLı olayları hakkında daha fazla bilgi için bkz. [bir arabirimdeki olaylar](../dotnet/how-to-use-events-in-cpp-cli.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, temsilci, olay ve olay işleyicilerinin çiftlerini bildiren bir bildirim gösterir. Olay işleyicilerini nasıl abone olunacağını (ekleme), çağırmayı ve sonra abonelikten çıkarmayacağını (kaldırmayı) gösterir.

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

```Output
OnClick: 7, 3.14159

OnDblClick: Hello
```

Aşağıdaki kod örneği, `raise` Önemsiz bir olay yöntemini oluşturmak için kullanılan mantığı gösterir. Olayda bir veya daha fazla abone varsa, `raise` yöntemi örtük olarak çağırmak veya temsilciyi açıkça çağırır. Temsilcinin dönüş türü yoksa **`void`** ve sıfır olay aboneleri varsa, `raise` Yöntem temsilci türü için varsayılan değeri döndürür. Hiçbir olay abonesi yoksa, `raise` yöntemi çağırmak hemen döndürülür ve hiçbir özel durum oluşturulmaz. Temsilci dönüş türü değilse **`void`** , temsilci türü döndürülür.

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

```Output
0

688
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
