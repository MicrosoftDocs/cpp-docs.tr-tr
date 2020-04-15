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
ms.openlocfilehash: 74022c8bc6af1d2cdf74fa452d4e0483637e542e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365524"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme

Aşağıdaki yönergeler ve örnekler, özel durumları nasıl yakalayıp sildiğinizi gösterir. **Denemeleri,** **yakalamaları**ve anahtar kelimeler **için** çoğunluk çalıştığı için çoğunluk ve hata kullanımı [için Modern C++ en iyi uygulamalarına bakın.](../cpp/errors-and-exception-handling-modern-cpp.md)

Özel durum işleyicileriniz, özel durum silmenin bir özel durum yakaladığında bellek sızıntısına neden olduğundan, işlettikleri özel durum nesnelerini silmeleri gerekir.

**Catch** bloğunuzun aşağıdaki anda bir özel durum silmesi gerekir:

- **Catch** bloğu yeni bir özel durum atar.

   Tabii ki, aynı özel durumu tekrar atarsanız özel durumu silmemelisiniz:

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Yürütme **yakalama** bloğu içinden döner.

> [!NOTE]
> Bir `CException`, özel durumu `Delete` silmek için üye işlevi kullanın silerken. Özel durum yığında yoksa başarısız olabileceğinden **silme** anahtar sözcüğünü kullanmayın.

#### <a name="to-catch-and-delete-exceptions"></a>Özel durumları yakalamak ve silmek için

1. **Try** bloğu ayarlamak için **try** anahtar sözcüklerini kullanın. **Deneme** bloğu içinde özel durum atabilecek program deyimlerini yürütün.

   **Catch** block'u ayarlamak için **catch** anahtar sözcüklerini kullanın. Özel durum işleme kodunu bir **catch** bloğuna yerleştirin. **Catch** bloğundaki kod, yalnızca **try** bloğu içindeki kod **catch** deyiminde belirtilen türe bir özel durum atarsa yürütülür.

   Aşağıdaki iskelet, **try** ve **catch** bloklarının normalde nasıl düzenlendiğini gösterir:

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   Bir özel durum atıldığında, denetim özel durum bildirimi özel durum türüyle eşleşen ilk **catch** bloğuna geçer. Aşağıda listelenmiş sıralı **yakalama** blokları ile farklı türde özel durumları seçerek işleyebilirsiniz:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Daha fazla bilgi için [bkz: MFC Özel Durum Makrolarından dönüştürme.](../mfc/exceptions-converting-from-mfc-exception-macros.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
