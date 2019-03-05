---
title: 'MFC ActiveX denetimleri: Özellikler'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: 5e01854e7ae7acdc33275351d0d26a76dfeabc9b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326419"
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX denetimleri: Özellikler

ActiveX denetimi denetim kapsayıcısı ile iletişim kurmak için olayları tetikler. Kapsayıcı, buna karşılık, yöntemleri ve özellikleri denetimi ile iletişim kurmak için kullanır. Yöntemleri ve özellikleri sırasıyla üye işlevleri ve üye değişkenleri bir C++ sınıfı için kullanın ve amacı, benzerdir. Herhangi bir kapsayıcıya gösterilen ActiveX denetiminin veri üyeleri özelliklerdir. Özellikler, Otomasyon istemcilerine ve ActiveX denetim kapsayıcıları gibi ActiveX denetimlerini içeren uygulamalar için bir arabirim sağlar.

Özellikler, öznitelikleri olarak da adlandırılır.

ActiveX denetim yöntemleri hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: Yöntemleri](../mfc/mfc-activex-controls-methods.md).

ActiveX denetimlerini, stok ve özel yöntemleri ve özellikleri uygulayabilir. Sınıf `COleControl` stok özellikleri bir uygulamasını sağlar. (Stok özelliklerinin tam listesi için bkz [MFC ActiveX denetimleri: Stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md).) Özel özellikler, geliştirici tarafından tanımlanan özel özellikleri bir ActiveX denetimine ekleyin. Daha fazla bilgi için [MFC ActiveX denetimleri: Özel Özellikler ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md).

Özel ve stok özelliklerini yöntemler gibi özellikleri ve yöntemleri ve var olan üye işlevlerini işleyen gönderme haritasını oluşan bir mekanizma tarafından desteklenen `COleControl` sınıfı. Ayrıca, bu özelliklerin Geliştirici denetimine ek bilgi geçirmek için kullandığı parametreleri olabilir.

Aşağıdaki makaleler ActiveX denetimi özelliklerini daha ayrıntılı açıklanmaktadır:

- [MFC ActiveX denetimleri: Stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [MFC ActiveX denetimleri: Özel Özellikler ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [MFC ActiveX denetimleri: Gelişmiş özellik uygulama](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [MFC ActiveX denetimleri: Ortam özelliklerine erişme](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
