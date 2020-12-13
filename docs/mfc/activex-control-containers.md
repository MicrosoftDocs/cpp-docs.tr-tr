---
description: 'Daha fazla bilgi edinin: ActiveX denetim kapsayıcıları'
title: ActiveX Denetim Kapsayıcıları
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
ms.openlocfilehash: 6de379cc152ff35e16366c1b5e920bf3548f4cd4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339117"
---
# <a name="activex-control-containers"></a>ActiveX Denetim Kapsayıcıları

ActiveX Denetim kapsayıcısı, ActiveX denetimlerini tam olarak destekleyen ve bunları kendi Windows veya iletişim kutularına birleştiresağlayan bir kapsayıcıdır. Bir ActiveX denetimi, birçok geliştirme projesinde kullanabileceğiniz, yeniden kullanılabilir bir yazılım öğesidir. Denetimler, uygulamanızın kullanıcısının veritabanlarına erişmesine, verileri izlemesine ve uygulamalarınızda çeşitli seçimler yapmasına izin verir. ActiveX denetimleri hakkında daha fazla bilgi için [MFC ActiveX denetimleri](mfc-activex-controls.md)makalesine bakın.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. Daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Denetim kapsayıcıları, genellikle bir projede iki form alır:

- İletişim kutusunda bir yerde ActiveX denetiminin kullanıldığı form görünümleri gibi iletişim kutuları ve iletişim kutusu gibi pencereler.

- Bir uygulamada, ActiveX denetiminin bir araç çubuğunda veya Kullanıcı penceresinde başka bir konumda kullanıldığı Windows.

ActiveX Denetim kapsayıcısı, sunulan [Yöntemler](mfc-activex-controls-methods.md) ve [Özellikler](mfc-activex-controls-properties.md)aracılığıyla denetimle etkileşime girer. Denetim kapsayıcısı tarafından erişilebilen ve değiştirilebilen bu yöntemlere ve özelliklere, ActiveX Denetim kapsayıcısı projesindeki bir sarmalayıcı sınıfı aracılığıyla erişilir. Katıştırılmış ActiveX denetimi, kapsayıcıyı bir eylem oluştuğunu bildirmek üzere [olayları](mfc-activex-controls-events.md) harekete geçirerek (göndererek) kapsayıcı ile de etkileşime geçebilir. Denetim kapsayıcısı bu bildirimlere göre işlem yapmak için seçim yapabilir.

Ek makaleler, bir ActiveX Denetim kapsayıcısı projesi oluşturmaktan Visual C++ ile oluşturulan ActiveX denetim kapsayıcılarıyla ilgili temel uygulama sorunlarına kadar çeşitli konuları ele almaktadır:

- [MFC ActiveX denetimi kapsayıcısı oluşturma](reference/creating-an-mfc-activex-control-container.md)

- [ActiveX denetimleri için kapsayıcılar](containers-for-activex-controls.md)

- [ActiveX denetim kapsayıcıları: ActiveX denetim kapsamayı El Ile etkinleştirme](activex-control-containers-manually-enabling-activex-control-containment.md)

- [ActiveX denetim kapsayıcıları: Denetim kapsayıcısı uygulamasına denetim ekleme](inserting-a-control-into-a-control-container-application.md)

- [ActiveX denetim kapsayıcıları: bir ActiveX denetimini üye değişkenine bağlama](activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [ActiveX denetim kapsayıcıları: ActiveX denetiminden olayları Işleme](activex-control-containers-handling-events-from-an-activex-control.md)

- [ActiveX denetim kapsayıcıları: denetim özelliklerini görüntüleme ve değiştirme](activex-control-containers-viewing-and-modifying-control-properties.md)

- [ActiveX denetim kapsayıcıları: ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama](programming-activex-controls-in-a-activex-control-container.md)

- [ActiveX denetim kapsayıcıları: Iletişim kutusu olmayan bir kapsayıcıda denetimleri kullanma](activex-control-containers-using-controls-in-a-non-dialog-container.md)

Bir iletişim kutusunda ActiveX denetimlerini kullanma hakkında daha fazla bilgi için, Iletişim kutusu [Düzenleyicisi](../windows/dialog-editor.md) konularına bakın.

Visual C++ ve MFC ActiveX denetim sınıfları kullanarak ActiveX denetimleri geliştirme ayrıntılarını açıklayan makalelerin listesi için bkz. [MFC ActiveX denetimleri](mfc-activex-controls.md). Makaleler, işlevsel kategorilere göre gruplandırılır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
