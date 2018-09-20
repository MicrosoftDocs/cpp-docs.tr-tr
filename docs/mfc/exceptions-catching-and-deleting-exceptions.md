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
ms.openlocfilehash: 5bd59cc19c80e305a7e57fb711a49f59a024d528
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434771"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme

Aşağıdaki yönergeler ve örnekler catch ve özel durumları silme işlemini göstermektedir. Daha fazla bilgi için **deneyin**, **catch**, ve **throw** anahtar bkz [C++ özel durum işleme](../cpp/cpp-exception-handling.md).

Bu kod bir özel durumu yakalar her bir bellek sızıntısı özel durum silme hatası neden olduğundan, özel durum işleyicileri işledikleri, özel durum nesneleri silmeniz gerekir.

**Catch** blok, bir özel durum silmelisiniz olduğunda:

- **Catch** bloğu yeni bir özel durum oluşturur.

     Elbette, tekrar aynı özel durum, özel durum silmemelisiniz:

     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Yürütme döndürür içinden **catch** blok.

> [!NOTE]
>  Silerken bir `CException`, kullanın `Delete` üye işlevi, özel durumu silinemedi. Kullanmayın **Sil** anahtar sözcüğü, çünkü özel durum yığın üzerinde değilse başarısız.

#### <a name="to-catch-and-delete-exceptions"></a>Catch ve özel durumları Sil

1. Kullanım **deneyin** ayarlamak için anahtar sözcüğü bir **deneyin** blok. İçinde bir özel durum oluşturabilecek herhangi bir programı deyim yürütme bir **deneyin** blok.

     Kullanım **catch** ayarlamak için anahtar sözcüğü bir **catch** blok. Özel durum işleme kodu yerleştirin bir **catch** blok. Kodda **catch** blokesi yalnızca içindeki kod **deneyin** blok, belirtilen türde bir özel durum oluşturursa **catch** deyimi.

     Aşağıdaki çatı gösterildiği nasıl **deneyin** ve **catch** blokları normal şekilde düzenlenmiştir:

     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

     Bir özel durum oluştuğunda denetim geçer ilk **catch** blok özel durum bildirimi eşleşen özel durumun türü. Farklı türde özel durum ile sıralı seçmeli olarak işleyebilir **catch** aşağıda listelenen engeller:

     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Daha fazla bilgi için [özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

