---
description: 'Hakkında daha fazla bilgi edinin: özel durumlar: özel durumları yakalama ve silme'
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
ms.openlocfilehash: 01f018694d211b4b60acc92c4121614d14769d6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290745"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Özel Durumlar: Özel Durumları Yakalama ve Silme

Aşağıdaki yönergeler ve örnekler, özel durumların nasıl yakalanalınacağını ve silineceğini gösterir. , Ve anahtar kelimeleri hakkında daha fazla bilgi için **`try`** **`catch`** **`throw`** bkz. [özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md).

Özel durum silme hatası, her kod bir özel durum yakalarsa bellek sızıntısına neden olduğundan özel durum İşleyicileriniz, işledikleri özel durum nesnelerini silmelidir.

**`catch`** Blobunun şu durumlarda bir özel durumu silmesi gerekir:

- **`catch`** Blok yeni bir özel durum oluşturur.

   Tabii ki, aynı özel durumu tekrar oluşturursanız özel durumu silmemelidir:

   [!code-cpp[NVC_MFCExceptions#3](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Yürütme blok içinden geri döner **`catch`** .

> [!NOTE]
> Bir silinirken `CException` , `Delete` özel durumu silmek için üye işlevini kullanın. **`delete`** Özel durum yığında değilse başarısız olabileceğinden anahtar sözcüğünü kullanmayın.

#### <a name="to-catch-and-delete-exceptions"></a>Özel durumları yakalamak ve silmek için

1. **`try`** Bir blok ayarlamak için anahtar sözcüğünü kullanın **`try`** . Bir blok içinde özel durum oluşturabilecek program deyimlerini yürütün **`try`** .

   **`catch`** Bir blok ayarlamak için anahtar sözcüğünü kullanın **`catch`** . Özel durum işleme kodunu bir blokta yerleştir **`catch`** . **`catch`** Bloktaki kod yalnızca blok içindeki kod, **`try`** bildiriminde belirtilen türde bir özel durum oluşturursa yürütülür **`catch`** .

   Aşağıdaki iskelet, nasıl **`try`** ve **`catch`** blokların nasıl düzenlendiğini gösterir:

   [!code-cpp[NVC_MFCExceptions#4](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   Bir özel durum oluştuğunda denetim, özel durum **`catch`** bildirimi özel durumun türüyle eşleşen ilk bloğa geçirilir. Aşağıda listelenen sıralı bloklarla farklı özel durum türlerini seçmeli **`catch`** olarak işleyebilirsiniz:

   [!code-cpp[NVC_MFCExceptions#5](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Daha fazla bilgi için bkz. [özel durumlar: MFC özel durum makrolarından dönüştürme](exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
