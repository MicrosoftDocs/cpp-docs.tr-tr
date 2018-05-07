---
title: 'Özel durumlar: Yakalama ve özel durumları silme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3527dabab96fe8f2832430f928a922941178ea97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme
Aşağıdaki yönergeler ve örnekler catch ve özel durumları silme gösterir. Daha fazla bilgi için **deneyin**, **catch**, ve `throw` anahtar sözcükler, bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md).  
  
 Bu kod bir özel durum yakalar her özel durum silme hatası bellek sızıntısı neden olduğundan, özel durum işleyicileri bunlar işlemek, özel durum nesneleri silmeniz gerekir.  
  
 **Catch** blok, bir özel durum silmelisiniz zaman:  
  
-   **Catch** blok yeni bir özel durum oluşturur.  
  
     Elbette, tekrar aynı özel durum, özel durum silmemeniz gerekir:  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   Yürütme döndürür içinden **catch** bloğu.  
  
> [!NOTE]
>  Silerken bir `CException`, kullanın **silmek** özel silmek için üye işlevi. Kullanmayın **silmek** anahtar sözcüğü, çünkü özel öbek üzerinde değilse, başarısız.  
  
#### <a name="to-catch-and-delete-exceptions"></a>Catch ve özel durumları silme  
  
1.  Kullanım **deneyin** ayarlamak için anahtar sözcüğü bir **deneyin** bloğu. İçinde bir özel durum yaratabilir herhangi program deyimlerini yürütmek bir **deneyin** bloğu.  
  
     Kullanım **catch** ayarlamak için anahtar sözcüğü bir **catch** bloğu. Özel durum işleme kodda yerleştirin bir **catch** bloğu. Kodda **catch** yalnızca blok yürütüldüğünde içindeki kod **deneyin** bloğu içinde belirtilen türde bir özel durum oluşturur **catch** deyimi.  
  
     Aşağıdaki iskelet gösterdiği nasıl **deneyin** ve **catch** blokları normal şekilde düzenlenmiştir:  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     Bir özel durum, Denetim geçirir ilk **catch** özel durum bildirimi eşleşen özel durum türü blok. Sıralı istisnalar farklı türlerde seçmeli olarak işleyebilir **catch** aşağıda listelenen engeller:  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 Daha fazla bilgi için bkz: [özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

