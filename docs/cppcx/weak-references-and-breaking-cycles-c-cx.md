---
description: 'Daha fazla bilgi edinin: zayıf başvurular ve ayırma döngüleri (C++/CX)'
title: Zayıf Başvurular ve Döngüleri Kesme (C++/CX)
ms.date: 01/22/2017
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
ms.openlocfilehash: 0c42081b0030ee697eab63fa519e2f6cbe4fe090
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288028"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Zayıf Başvurular ve Döngüleri Kesme (C++/CX)

Başvuru sayımını temel alan herhangi bir tür sisteminde, türlere yapılan başvurular *döngü* oluşturabilir. diğer bir deyişle, bir nesne ikinci bir nesneye başvuruyorsa, ikinci nesne üçüncü bir nesneye başvurur ve bu nedenle bir son nesne ilk nesneye geri başvurana kadar devam eder. Bir döngüde, bir nesnenin başvuru sayısı sıfır olduğunda nesneler doğru şekilde silinemez. C++/CX, bu sorunu çözmenize yardımcı olmak için [Platform:: WeakReference Sınıf](../cppcx/platform-weakreference-class.md) sınıfını sağlar. Nesnesi `WeakReference` artık yoksa null değeri döndüren [Resolve](../cppcx/platform-weakreference-class.md#resolve) yöntemini destekler veya nesne etkin ancak türü değilse bir [Platform:: InvalidCastException](../cppcx/platform-invalidcastexception-class.md) oluşturur `T` .

' In kullanılması gereken bir senaryo, `WeakReference` **`this`** işaretçinin bir olay işleyicisini tanımlamak için kullanılan bir lambda ifadesinde yakalanmasının bir senaryodur. Olay işleyicileri tanımlarken adlandırılmış yöntemler kullanmanızı öneririz, ancak olay işleyiciniz için bir lambda kullanmak isterseniz veya bir başvuru sayımı döngüsünü başka bir durumda kesmeniz gerekiyorsa kullanın `WeakReference` . Aşağıda bir örnek verilmiştir:

```

using namespace Platform::Details;
using namespace Windows::UI::Xaml;
using namespace Windows::UI::Xaml::Input;
using namespace Windows::UI::Xaml::Controls;

Class1::Class1()
{
    // Class1 has a reference to m_Page
    m_Page = ref new Page();

    // m_Page will have a reference to this Class1
    // so create a weak reference to this
    WeakReference wr(this);
    m_Page->DoubleTapped += ref new DoubleTappedEventHandler(
        [wr](Object^ sender, DoubleTappedRoutedEventArgs^ args)
    {
       // Use the weak reference to get the object
       Class1^ c = wr.Resolve<Class1>();
       if (c != nullptr)
       {
           c->m_eventFired = true;
       }
       else
       {
           // Inform the event that this handler should be removed
           // from the subscriber list
           throw ref new DisconnectedException();
       }
    });
}

}
```

Bir olay işleyicisi oluşturduğunda `DisconnectedException` , etkinliğin abonelik listesinden işleyiciyi kaldırmasına neden olur.
