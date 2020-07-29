---
title: event (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
ms.openlocfilehash: 8a0674defb0f5e81e0d1417bab5a282cf82b82b3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195700"
---
# <a name="event--ccli-and-ccx"></a>event (C++/CLI ve C++/CX)

**Event** anahtar sözcüğü, ilgilendiğiniz abonelere (*olay işleyicileri*) bir bildirimin oluştuğunu bildiren bir *olay*bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

C++/CX, bir *olay üyesinin* veya bir *olay bloğunun*bildirimini destekler. Olay üyesi bir olay bloğunu bildirmek için toplu bir özelliktir. Varsayılan olarak, bir olay üyesi, `add()` `remove()` , ve `raise()` bir olay bloğunda açıkça belirtilen işlevleri bildirir. Bir olay üyesinde işlevleri özelleştirmek için, bunun yerine bir olay bloğu bildirin ve ardından ihtiyacınız olan işlevleri geçersiz kılın.

### <a name="syntax"></a>Söz dizimi

```cpp
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

### <a name="parameters"></a>Parametreler

*icisi*<br/>
Olay bildiriminde veya bir olay erişimci yönteminde kullanılabilen bir değiştirici.  Olası değerler şunlardır **`static`** **`virtual`** .

*ğini*<br/>
İmza olay işleyicisinin eşleşmesi gereken [temsilci](delegate-cpp-component-extensions.md).

*event_name*<br/>
Olayın adı.

*return_value*<br/>
Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir olması için, dönüş türü olmalıdır **`void`** .

*parametrelere*<br/>
seçim `raise`Metot için *temsilci* parametresinin imzasıyla eşleşen parametreler.

### <a name="remarks"></a>Açıklamalar

Bir olay, bir temsilci ile olayın tetiklenmesine yanıt veren bir üye işlev (olay işleyicisi) arasındaki bir ilişkidir ve herhangi bir sınıftan istemcilerin, temeldeki temsilcinin imzasıyla ve dönüş türüyle uyumlu yöntemler kaydetmesini sağlar.

İki tür olay bildirimi vardır:

*Olay veri üyesi*<br/>
Derleyici, temsilci türünün bir üyesi olan olay için otomatik olarak depolama oluşturur ve iç `add()` , `remove()` ve `raise()` üye işlevleri oluşturur. Bir olay veri üyesinin bir sınıf içinde bildirilmelidir olması gerekir. Temsilcinin dönüş türünün dönüş türü, olay işleyicisinin dönüş türü ile aynı olmalıdır.

*olay bloğu*<br/>
Bir olay bloğu,, ve yöntemlerinin davranışını açık bir şekilde bildirmenize ve özelleştirmenize olanak sağlar `add()` `remove()` `raise()` .

Bir olay işleyicisi eklemek ve kaldırmak için **işleçlerini + =** ve **operator-=** kullanabilirsiniz ya da `add()` ve `remove()` yöntemlerini açıkça çağırabilirsiniz.

**olay** , bağlama duyarlı bir anahtar sözcüktür; daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Olaylar (C++/CX)](../cppcx/events-c-cx.md).

Bir olay işleyicisini eklemek ve kaldırmak istiyorsanız, ekleme işlemi tarafından döndürülen EventRegistrationToken yapısını kaydetmeniz gerekir. Ardından, kaldır işleminde, kaldırılacak olay işleyicisini belirlemek için kaydedilmiş EventRegistrationToken yapısını kullanmanız gerekir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Event** anahtar sözcüğü bir olay bildirmenize olanak tanır. Bir olay, bir sınıfın bir şey olduğunda bildirim sağlaması için bir yoldur.

### <a name="syntax"></a>Söz dizimi

```cpp
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

### <a name="parameters"></a>Parametreler

*icisi*<br/>
Olay bildiriminde veya bir olay erişimci yönteminde kullanılabilen bir değiştirici.  Olası değerler şunlardır **`static`** **`virtual`** .

*ğini*<br/>
İmza olay işleyicisinin eşleşmesi gereken [temsilci](delegate-cpp-component-extensions.md).

*event_name*<br/>
Olayın adı.

*return_value*<br/>
Olay erişimci yönteminin dönüş değeri.  Doğrulanabilir olması için, dönüş türü olmalıdır **`void`** .

*parametrelere*<br/>
seçim `raise`Metot için *temsilci* parametresinin imzasıyla eşleşen parametreler.

### <a name="remarks"></a>Açıklamalar

Bir olay, bir temsilci ile olayın tetiklenmesine yanıt veren bir üye işlev (olay işleyicisi) arasındaki bir ilişkidir ve herhangi bir sınıftan istemcilerin, temeldeki temsilcinin imzasıyla ve dönüş türüyle uyumlu yöntemler kaydetmesini sağlar.

Temsilcinin, kodunuzun olayın oluştuğunu gösterdiği zaman çağrılacak bir veya daha fazla ilişkili yöntemi olabilir. Bir programdaki bir olay, .NET Framework ortak dil çalışma zamanını hedefleyen diğer programlar için kullanılabilir hale getirilebilir.

İki tür olay bildirimi vardır:

*Olay veri üyeleri*<br/>
Temsilci türünün bir üyesi olan olay için depolama alanı, veri üyesi olayları için derleyici tarafından oluşturulur.  Bir olay veri üyesinin bir sınıf içinde bildirilmelidir olması gerekir. Bu, önemsiz bir olay olarak da bilinir (Aşağıdaki kod örneğine bakın.)

*olay blokları*<br/>
Olay blokları, Add, Remove ve raise yöntemlerini uygulayarak ekleme, kaldırma ve yükseltme yöntemlerinin davranışını özelleştirmenize olanak sağlar. Add, Remove ve raise Yöntemlerinin imzası temsilcinin imzasıyla aynı olmalıdır.  Olay engelleme olayları veri üyeleri değildir ve veri üyesi olarak herhangi bir kullanım, derleyici hatası oluşturur.

Olay işleyicisinin dönüş türü, temsilcinin dönüş türüyle aynı olmalıdır.

.NET Framework, bir veri üyesini bir yöntemin kendisi (yani, `Invoke` karşılık gelen temsilcinin yöntemi) gibi kabul edebilirsiniz. Yönetilen bir olay veri üyesini bildirmek için temsilci türünü önceden tanımlamanız gerekir. Bunun aksine, yönetilen bir olay yöntemi zaten tanımlı değilse karşılık gelen yönetilen temsilciyi örtülü olarak tanımlar.  Örnek için bu konunun sonundaki kod örneğine bakın.

Yönetilen bir olay bildirirken, işleç + = ve-= kullanılarak olay işleyicileri eklendiğinde veya kaldırıldığında çağrılacak ekleme ve kaldırma erişimcileri belirtebilirsiniz. Ekle, kaldır ve Yükselt yöntemleri açıkça çağrılabilir.

Visual C++ olaylar oluşturmak ve kullanmak için aşağıdaki adımlar gerçekleştirilmelidir:

1. Bir temsilci oluşturun veya seçin. Kendi olaylarınızı tanımlıyorsanız, **olay** anahtar sözcüğüyle birlikte kullanmak için bir temsilci olduğundan da emin olmanız gerekir. Olay önceden öntanımlı ise, .NET Framework Örneğin, olay tüketicilerinin yalnızca temsilcinin adını bilmeleri gerekir.

2. Şunu içeren bir sınıf oluşturun:

   - Temsilciden oluşturulan bir olay.

   - Seçim **Olay** anahtar sözcüğüyle belirtilen temsilcinin bir örneğinin var olduğunu doğrulayan bir yöntem. Aksi takdirde, bu mantık olayını harekete uygulayan koda yerleştirilmelidir.

   - Olayı çağıran Yöntemler. Bu yöntemler bazı temel sınıf işlevlerinin geçersiz kılmaları olabilir.

   Bu sınıf, olayı tanımlar.

3. Olayları olaya bağlayan bir veya daha fazla sınıf tanımlayın. Bu sınıfların her biri, temel sınıftaki olayla bir veya daha fazla yöntemi ilişkilendirir.

4. Olayı kullanın:

   - Olay bildirimini içeren sınıfın bir nesnesini oluşturun.

   - Olay tanımını içeren sınıfın bir nesnesini oluşturun.

C++/CLı olayları hakkında daha fazla bilgi için bkz.

- [Arabirimdeki olaylar](../dotnet/how-to-use-events-in-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, temsilci, olay ve olay işleyicisi çiftlerinin bildirimini gösterir; olay işleyicilerini abone olma (ekleme); olay işleyicilerini çağırma; ve sonra olay işleyicilerini aboneliği kaldırma (kaldırma).

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

Aşağıdaki kod örneği, önemsiz bir olayın yöntemini oluşturmak için kullanılan mantığı gösterir `raise` : olayda bir veya daha fazla abone varsa, `raise` yöntemi örtük olarak çağırarak veya açıkça temsilciyi çağıran bir. Temsilcinin dönüş türü değilse **`void`** ve sıfır olay aboneleri varsa, `raise` Yöntem temsilci türü için varsayılan değeri döndürür. Hiçbir olay abonesi yoksa, `raise` yöntemini çağırmak yalnızca döndürür ve hiçbir özel durum oluşturulmaz. Temsilci dönüş türü değilse **`void`** , temsilci türü döndürülür.

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
