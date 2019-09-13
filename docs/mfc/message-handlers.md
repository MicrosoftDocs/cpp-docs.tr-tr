---
title: İleti İşleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
ms.openlocfilehash: 25805187f88c5423ea41cd7cbe346e44e7d7d36a
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907455"
---
# <a name="message-handlers"></a>İleti İşleyicileri

MFC 'de, ayrılmış bir *işleyici* işlevi her ayrı iletiyi işler. İleti işleyici işlevleri bir sınıfın üye işlevleridir. Bu belgelerde *ileti işleyici üye işlevi*, *ileti işleyici işlevi*, *ileti işleyicisi*ve *işleyicinin* birbirlerinin yerine kullanıldığı terimler kullanılmaktadır. Bazı ileti işleyicileri türleri "komut işleyicileri" olarak da adlandırılır.

Çerçeve uygulaması yazarken çalışmanızın büyük bir oranı için ileti işleyicileri hesapları yazma. Bu makale ailesinde ileti işleme mekanizmasının nasıl çalıştığı açıklanmaktadır.

İleti için işleyici, bu iletiye yanıt vermek istediğiniz her şeyi yapar. , Sınıfının [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanarak işleyicileri oluşturabilir ve ardından kaynak kodu düzenleyicisini kullanarak işleyicinin kodunu doldurabilirsiniz.

İşleyicilerinizi yazmak için Microsoft Visual C++ ve MFC 'nin tüm özelliklerini kullanabilirsiniz. Tüm sınıfların bir listesi için bkz. *MFC başvurusunda* [sınıf kitaplığına genel bakış](../mfc/class-library-overview.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)
