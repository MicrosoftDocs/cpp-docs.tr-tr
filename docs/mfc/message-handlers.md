---
description: 'Daha fazla bilgi için: Ileti Işleyicileri'
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
ms.openlocfilehash: dc3f52956f125542ef0c5d879543f1e8a49e803b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203373"
---
# <a name="message-handlers"></a>İleti İşleyicileri

MFC 'de, ayrılmış bir *işleyici* işlevi her ayrı iletiyi işler. İleti işleyici işlevleri bir sınıfın üye işlevleridir. Bu belgelerde *ileti işleyici üye işlevi*, *ileti işleyici işlevi*, *ileti işleyicisi* ve *işleyicinin* birbirlerinin yerine kullanıldığı terimler kullanılmaktadır. Bazı ileti işleyicileri türleri "komut işleyicileri" olarak da adlandırılır.

Çerçeve uygulaması yazarken çalışmanızın büyük bir oranı için ileti işleyicileri hesapları yazma. Bu makale ailesinde ileti işleme mekanizmasının nasıl çalıştığı açıklanmaktadır.

İleti için işleyici, bu iletiye yanıt vermek istediğiniz her şeyi yapar. , Sınıfının [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanarak işleyicileri oluşturabilir ve ardından kaynak kodu düzenleyicisini kullanarak işleyicinin kodunu doldurabilirsiniz.

İşleyicilerinizi yazmak için Microsoft Visual C++ ve MFC 'nin tüm özelliklerini kullanabilirsiniz. Tüm sınıfların bir listesi için bkz. *MFC başvurusunda* [sınıf kitaplığına genel bakış](class-library-overview.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede iletiler ve komutlar](messages-and-commands-in-the-framework.md)
