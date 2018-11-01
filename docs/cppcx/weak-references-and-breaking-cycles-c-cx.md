---
title: Zayıf başvurular ve döngüleri kesme (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
ms.openlocfilehash: e035f298100408bd16b1087439d3ce5ac057fd2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572906"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Zayıf başvurular ve döngüleri kesme (C + +/ CX)

Başvuru türleri için başvuru sayımı alan hiçbir tür sistemindeki kurabilir *döngüleri*— diğer bir deyişle, bir nesne, ikinci bir nesneye başvurur, ikinci nesne bazı son nesnenin geri başvurduğu kadar üçüncü vb. nesnesini ifade eder. ilk nesne. Bir nesnenin başvuru sayısının sıfır olduğunda bir döngüsünde doğru nesneler silinemiyor. Bu sorun, C + gidermenize yardımcı olacak +/ CX sağlar [Platform::WeakReference sınıfı](../cppcx/platform-weakreference-class.md) sınıfı. A `WeakReference` nesnesi [çözmek](../cppcx/platform-weakreference-class.md#resolve) nesnesi artık yok veya oluşturur, null döndüren yöntemi bir [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) nesne, Canlı ancak türündedeğil`T`.

Bir senaryoda `WeakReference` kullanılmalıdır olduğunda `this` işaretçi bir olay işleyicisi tanımlamak için kullanılan bir lambda ifadesinde yakalanan. Olay işleyicilerini tanımlar, ancak bir lambda, olay işleyicisi için kullanmak istediğiniz adlandırılmış yöntemleri kullanmanızı öneririz — ya da diğer bazı durumlarda döngü sayımı bir başvuru ayırmak varsa — kullanın `WeakReference`. Örnek buradadır:

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

Ne zaman bir olay işleyicisi oluşturur `DisconnectedException`, olay işleyicisi abone listeden kaldırmak neden olur.

## <a name="see-also"></a>Ayrıca Bkz.

