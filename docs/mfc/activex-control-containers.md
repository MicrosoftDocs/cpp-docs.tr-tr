---
title: ActiveX Denetim Kapsayıcıları
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
ms.openlocfilehash: e8340acafc81447052fcb8d90df8997e81dc4117
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394864"
---
# <a name="activex-control-containers"></a>ActiveX Denetim Kapsayıcıları

Bir ActiveX denetimi kapsayıcısı, tam olarak ActiveX denetimlerini destekleyen bir kapsayıcıdır ve bunları kendi windows veya iletişim kutularının dahil edebilirsiniz. ActiveX denetimi birçok geliştirme projelerinde kullanabileceğiniz yeniden kullanılabilir yazılım bir öğedir. Denetimler, veritabanlarına erişim, verileri izleyin ve uygulamalarınızı içindeki çeşitli seçimleri yapmak, uygulamanızın kullanıcı izin verir. ActiveX denetimleri hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md).

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX denetimlerini](activex-controls.md).

Denetimi kapsayıcıları, genellikle bir projede iki forms uygulayın:

- İletişim kutuları ve iletişim kutusuna ActiveX denetimi yere kullanıldığı iletişim benzeri windows form görünümleri gibi.

- Burada bir ActiveX denetimi, bir uygulamada Windows araç çubuğu veya başka bir konuma kullanıcı penceresinde kullanılır.

ActiveX denetimi kapsayıcısı etkileşim denetimi ile kullanıma sunulan [yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md). Bu yöntemlere ve özelliklere erişim ve denetim kapsayıcı tarafından değiştirildiğinde, ActiveX denetimi kapsayıcısı projedeki bir sarmalayıcı sınıfı aracılığıyla erişilir. Katıştırılmış ActiveX denetimi da kapsayıcıyla (gönderen) tetikleme tarafından etkileşimde bulunabilirsiniz [olayları](../mfc/mfc-activex-controls-events.md) bir eylem oluştuktan kapsayıcı bildirir. Denetim kapsayıcısı veya bu bildirimleri hareket seçebilirsiniz.

Diğer makaleler, Visual C++ ile oluşturulan ActiveX denetimi kapsayıcıları temel uygulama sorunları için bir ActiveX denetimi kapsayıcısı proje oluşturmasını çeşitli konular açıklanmaktadır:

- [MFC ActiveX Denetimi Kapsayıcısı Oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md)

- [ActiveX Denetimleri için Kapsayıcılar](../mfc/containers-for-activex-controls.md)

- [ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)

- [ActiveX Denetimi Kapsayıcıları: Denetim Kapsayıcısı Uygulamasına Denetim Ekleme](../mfc/inserting-a-control-into-a-control-container-application.md)

- [ActiveX Denetimi Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [ActiveX Denetimi Kapsayıcıları: ActiveX denetimindeki etkinlikleri işleme](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)

- [ActiveX Denetimi Kapsayıcıları: Denetim Özelliklerini Görüntüleme ve Değiştirme](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)

- [ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsayıcısındaki ActiveX Denetimlerini Programlama](../mfc/programming-activex-controls-in-a-activex-control-container.md)

- [ActiveX Denetimi Kapsayıcıları: Denetimleri İletişim Kutusu Olmayan Kapsayıcılarda Kullanma](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)

Bir iletişim kutusuna ActiveX denetimleri hakkında daha fazla bilgi için bkz. [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) konuları.

Visual C++ ve MFC ActiveX denetim sınıfları kullanarak ActiveX denetimleri geliştirme ayrıntılarını açıklayan makalelerin listesi için bkz. [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md). Makaleleri işlevsel kategorilere göre gruplandırılır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
