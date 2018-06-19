---
title: Zayıf başvurular ve kesme döngüleri (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48b5d73d85383056b17c806e061b131b12d821a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089084"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Zayıf başvurular ve kesme döngüleri (C + +/ CX)
Başvuru sayım dayalı herhangi türü sistemde, tür başvuruları kurabilir *döngüleri*— diğer bir deyişle, bir nesne ikinci bir nesneye başvuruyor, bazı son nesnenin geri başvurduğu kadar üçüncü, vb. nesne ikinci nesneden başvuruyor ilk nesne. Bir nesnenin başvuru sayısı sıfır olduğunda bir döngüsünde doğru nesneleri silinemiyor. Bu sorun, C + gidermenize yardımcı olacak +/ CX sağlar [Platform::WeakReference sınıfı](../cppcx/platform-weakreference-class.md) sınıfı. A `WeakReference` nesnesi [gidermek](../cppcx/platform-weakreference-class.md#resolve) nesne artık var veya oluşturur, null döndüren yöntemi bir [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) nesne Canlı ancak türündedeğil`T`.  
  
 Bir senaryoda `WeakReference` kullanılmalıdır olduğunda `this` işaretçi, olay işleyici tanımlamak için kullanılan bir lambda ifadesinde yakalanır. Olay işleyicileri tanımladığınızda, ancak bir lambda, olay işleyicisi için kullanmak istiyorsanız, adlandırılmış yöntemleri kullanmanızı öneririz; veya bir başvuru diğer bir durum döngüsünde sayım bölüneceği varsa — kullanmak `WeakReference`. Örnek buradadır:  
  
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
  
 Ne zaman bir olay işleyicisi oluşturur `DisconnectedException`, olay işleyici abone listesinden kaldırmak neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  


