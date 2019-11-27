---
title: 'Özel Durumlar: Özel Durumları Yakalama ve Silme'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 0142ffddfb391ae8da878d9e5fe34629cf16cb52
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246698"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme

Aşağıdaki yönergeler ve örnekler, özel durumların nasıl yakalanalınacağını ve silineceğini gösterir. **TRY**, **catch**ve **throw** anahtar sözcükleri hakkında daha fazla bilgi için bkz. [özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md).

Özel durum silme hatası, her kod bir özel durum yakalarsa bellek sızıntısına neden olduğundan özel durum İşleyicileriniz, işledikleri özel durum nesnelerini silmelidir.

**Catch** blobunun şu durumlarda bir özel durumu silmesi gerekir:

- **Catch** bloğu yeni bir özel durum oluşturur.

   Tabii ki, aynı özel durumu tekrar oluşturursanız özel durumu silmemelidir:

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Yürütme, **catch** bloğunun içinden geri döner.

> [!NOTE]
>  Bir `CException`silinirken, özel durumu silmek için `Delete` member işlevini kullanın. Özel durum yığında değilse başarısız olabileceğinden **Delete** anahtar sözcüğünü kullanmayın.

#### <a name="to-catch-and-delete-exceptions"></a>Özel durumları yakalamak ve silmek için

1. **TRY anahtar sözcüğünü** kullanarak bir **TRY** bloğu ayarlayın. Bir **TRY** bloğu içinde özel durum oluşturabilecek program deyimlerini yürütün.

   **Catch bloğunu ayarlamak** için **catch** anahtar sözcüğünü kullanın. Özel durum işleme kodunu bir **catch** bloğuna yerleştirin. **Catch** bloğundaki kod yalnızca **TRY** bloğu içindeki kod **catch** ifadesinde belirtilen türde bir özel durum oluşturursa yürütülür.

   Aşağıdaki iskelet, **TRY** ve **catch** bloklarının normal şekilde nasıl düzenlendiğini göstermektedir:

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   Bir özel durum oluştuğunda denetim, özel durum bildirimi özel durumun türüyle eşleşen ilk **catch** bloğuna geçer. Aşağıda listelenen sıralı **catch** blokları ile farklı özel durum türlerini seçmeli olarak işleyebilirsiniz:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Daha fazla bilgi için bkz. [özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
