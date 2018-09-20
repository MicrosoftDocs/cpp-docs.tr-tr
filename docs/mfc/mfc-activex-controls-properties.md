---
title: 'MFC ActiveX denetimleri: Özellikler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27cdbd548366bcf02e2d6282b309402cf25af2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401621"
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX Denetimleri: Özellikler

ActiveX denetimi denetim kapsayıcısı ile iletişim kurmak için olayları tetikler. Kapsayıcı, buna karşılık, yöntemleri ve özellikleri denetimi ile iletişim kurmak için kullanır. Yöntemleri ve özellikleri sırasıyla üye işlevleri ve üye değişkenleri bir C++ sınıfı için kullanın ve amacı, benzerdir. Herhangi bir kapsayıcıya gösterilen ActiveX denetiminin veri üyeleri özelliklerdir. Özellikler, Otomasyon istemcilerine ve ActiveX denetim kapsayıcıları gibi ActiveX denetimlerini içeren uygulamalar için bir arabirim sağlar.

Özellikler, öznitelikleri olarak da adlandırılır.

ActiveX denetim yöntemleri hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md).

ActiveX denetimlerini, stok ve özel yöntemleri ve özellikleri uygulayabilir. Sınıf `COleControl` stok özellikleri bir uygulamasını sağlar. (Stok özelliklerinin tam listesi için bkz [MFC ActiveX denetimleri: stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md).) Özel özellikler, geliştirici tarafından tanımlanan özel özellikleri bir ActiveX denetimine ekleyin. Daha fazla bilgi için [MFC ActiveX denetimleri: özel özellikler ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md).

Özel ve stok özelliklerini yöntemler gibi özellikleri ve yöntemleri ve var olan üye işlevlerini işleyen gönderme haritasını oluşan bir mekanizma tarafından desteklenen `COleControl` sınıfı. Ayrıca, bu özelliklerin Geliştirici denetimine ek bilgi geçirmek için kullandığı parametreleri olabilir.

Aşağıdaki makaleler ActiveX denetimi özelliklerini daha ayrıntılı açıklanmaktadır:

- [MFC ActiveX Denetimleri: Stok Özellikler Ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [MFC ActiveX Denetimleri: Özel Özellikler Ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [MFC ActiveX Denetimleri: Ortam Özelliklerine Erişme](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

