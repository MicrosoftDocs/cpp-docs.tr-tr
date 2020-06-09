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
ms.openlocfilehash: f9c5272b513a92dc6dcfa37559b00ae79b658918
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619972"
---
# <a name="message-handlers"></a>İleti İşleyicileri

MFC 'de, ayrılmış bir *işleyici* işlevi her ayrı iletiyi işler. İleti işleyici işlevleri bir sınıfın üye işlevleridir. Bu belgelerde *ileti işleyici üye işlevi*, *ileti işleyici işlevi*, *ileti işleyicisi*ve *işleyicinin* birbirlerinin yerine kullanıldığı terimler kullanılmaktadır. Bazı ileti işleyicileri türleri "komut işleyicileri" olarak da adlandırılır.

Çerçeve uygulaması yazarken çalışmanızın büyük bir oranı için ileti işleyicileri hesapları yazma. Bu makale ailesinde ileti işleme mekanizmasının nasıl çalıştığı açıklanmaktadır.

İleti için işleyici, bu iletiye yanıt vermek istediğiniz her şeyi yapar. , Sınıfının [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanarak işleyicileri oluşturabilir ve ardından kaynak kodu düzenleyicisini kullanarak işleyicinin kodunu doldurabilirsiniz.

İşleyicilerinizi yazmak için Microsoft Visual C++ ve MFC 'nin tüm özelliklerini kullanabilirsiniz. Tüm sınıfların bir listesi için bkz. *MFC başvurusunda* [sınıf kitaplığına genel bakış](class-library-overview.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](messages-and-commands-in-the-framework.md)
