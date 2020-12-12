---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: bir yöntemden hata kodları döndürme'
title: 'MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: f6a1f372442ee67787a7a5421dabb4460acfcc7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206077"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme

Bu makalede, bir ActiveX denetim yönteminden hata kodlarının nasıl döndürülayarlanacağı açıklanır.

Bir yöntem içinde bir hata oluştuğunu göstermek için bir parametre olarak bir SCODE (durum kodu) alan [COleControl:: ThrowError](reference/colecontrol-class.md#throwerror) member işlevini kullanmanız gerekir. Önceden tanımlanmış bir SCODE kullanabilir veya kendi kendinize birini tanımlayabilirsiniz.

> [!NOTE]
> `ThrowError` , bir özelliğin get veya set işlevi ya da bir otomasyon yöntemi içinden bir hata döndürmesinin bir yolu olarak kullanılmak üzere tasarlanmıştır. Bunlar, uygun özel durum işleyicisinin yığında mevcut olacağı tek zamanlardır.

[Coelcontrol:: SetNotSupported](reference/colecontrol-class.md#setnotsupported), [Cohancontrol:: GetNotSupported](reference/colecontrol-class.md#getnotsupported)ve Cotacontrol:: [setnotizin verilen](reference/colecontrol-class.md#setnotpermitted)en yaygın önceden tanımlanmış SCODEs için yardımcı işlevler mevcuttur.

Özel SCODEs tanımlanmasıyla ilgili önceden tanımlanmış SCODEs ve yönergelerin bir listesi için, ActiveX denetimlerinde [ActiveX denetiminizdeki hataları işleme](mfc-activex-controls-advanced-topics.md) bölümüne bakın: gelişmiş konular.

Kodunuzun diğer alanlarındaki özel durumları raporlama hakkında daha fazla bilgi için bkz. [COleControl:: FireError](reference/colecontrol-class.md#fireerror) ve ActiveX denetimlerinde [hataları işleme](mfc-activex-controls-advanced-topics.md) başlıklı Bölüm: gelişmiş konular.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
