---
title: 'MFC ActiveX Denetimleri: Özellikler'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: c7ed0fddea660409f5089159b71d39a29b01d538
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618181"
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX Denetimleri: Özellikler

Bir ActiveX denetimi, Denetim kapsayıcısı ile iletişim kurmak için olayları harekete geçirilir. ' Deki kapsayıcı, denetimle iletişim kurmak için yöntemler ve Özellikler kullanır. Yöntemler ve özellikler, sırasıyla üye işlevleri ve bir C++ sınıfının üye değişkenleri için kullanımda ve amaca benzer. Özellikler, herhangi bir kapsayıcıya sunulan ActiveX denetiminin veri üyeleridir. Özellikler, Otomasyon istemcileri ve ActiveX denetim kapsayıcıları gibi ActiveX denetimleri içeren uygulamalar için bir arabirim sağlar.

Özellikler de öznitelikler olarak adlandırılır.

ActiveX denetim yöntemleriyle ilgili daha fazla bilgi için [MFC ActiveX denetimleri: Yöntemler](mfc-activex-controls-methods.md)makalesine bakın.

ActiveX denetimleri hem hisse senedi hem de özel yöntemler ve Özellikler uygulayabilir. Sınıf `COleControl` , stok özellikleri için bir uygulama sağlar. (Hisse senedi özelliklerinin tamamı listesi için bkz. [MFC ActiveX denetimleri: stok özellikleri ekleme](mfc-activex-controls-adding-stock-properties.md).) Geliştirici tarafından tanımlanan özel özellikler, bir ActiveX denetimine özelleştirilmiş özellikler ekler. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri: özel özellikler ekleme](mfc-activex-controls-adding-custom-properties.md).

Yöntemler gibi hem özel hem de stok özellikleri, sınıfın özelliklerini ve yöntemlerini ve varolan üye işlevlerini işleyen bir dağıtım eşlemesinden oluşan bir mekanizma tarafından desteklenir `COleControl` . Ayrıca, bu özelliklerde, geliştiricinin ek bilgileri denetime iletmek için kullandığı parametreler bulunabilir.

Aşağıdaki makaleler, ActiveX denetim özelliklerini daha ayrıntılı bir şekilde ele almaktadır:

- [MFC ActiveX Denetimleri: Stok Özellikler Ekleme](mfc-activex-controls-adding-stock-properties.md)

- [MFC ActiveX Denetimleri: Özel Özellikler Ekleme](mfc-activex-controls-adding-custom-properties.md)

- [MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama](mfc-activex-controls-advanced-property-implementation.md)

- [MFC ActiveX Denetimleri: Ortam Özelliklerine Erişme](mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
