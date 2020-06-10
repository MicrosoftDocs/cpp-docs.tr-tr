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
ms.openlocfilehash: 50e3a3f8c064b2a054f0018e87c4e8782a5dc363
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618843"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme

Aşağıdaki yönergeler ve örnekler, özel durumların nasıl yakalanalınacağını ve silineceğini gösterir. **TRY**, **catch**ve **throw** anahtar sözcükleri hakkında daha fazla bilgi için bkz. [özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md).

Özel durum silme hatası, her kod bir özel durum yakalarsa bellek sızıntısına neden olduğundan özel durum İşleyicileriniz, işledikleri özel durum nesnelerini silmelidir.

**Catch** blobunun şu durumlarda bir özel durumu silmesi gerekir:

- **Catch** bloğu yeni bir özel durum oluşturur.

   Tabii ki, aynı özel durumu tekrar oluşturursanız özel durumu silmemelidir:

   [!code-cpp[NVC_MFCExceptions#3](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Yürütme, **catch** bloğunun içinden geri döner.

> [!NOTE]
> Bir silinirken `CException` , `Delete` özel durumu silmek için üye işlevini kullanın. Özel durum yığında değilse başarısız olabileceğinden **Delete** anahtar sözcüğünü kullanmayın.

#### <a name="to-catch-and-delete-exceptions"></a>Özel durumları yakalamak ve silmek için

1. **TRY anahtar sözcüğünü** kullanarak bir **TRY** bloğu ayarlayın. Bir **TRY** bloğu içinde özel durum oluşturabilecek program deyimlerini yürütün.

   **Catch bloğunu ayarlamak** için **catch** anahtar sözcüğünü kullanın. Özel durum işleme kodunu bir **catch** bloğuna yerleştirin. **Catch** bloğundaki kod yalnızca **TRY** bloğu içindeki kod **catch** ifadesinde belirtilen türde bir özel durum oluşturursa yürütülür.

   Aşağıdaki iskelet, **TRY** ve **catch** bloklarının normal şekilde nasıl düzenlendiğini göstermektedir:

   [!code-cpp[NVC_MFCExceptions#4](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   Bir özel durum oluştuğunda denetim, özel durum bildirimi özel durumun türüyle eşleşen ilk **catch** bloğuna geçer. Aşağıda listelenen sıralı **catch** blokları ile farklı özel durum türlerini seçmeli olarak işleyebilirsiniz:

   [!code-cpp[NVC_MFCExceptions#5](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Daha fazla bilgi için bkz. [özel durumlar: MFC özel durum makrolarından dönüştürme](exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
