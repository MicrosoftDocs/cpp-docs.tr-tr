---
title: "Zayıf başvurular ve kesme döngüleri (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: f769169f7a101e2f330ea7787401895d05778260
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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


