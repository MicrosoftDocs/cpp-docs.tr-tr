---
title: 'MFC ActiveX denetimleri: Bir Metottan hata kodları döndürme'
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
ms.openlocfilehash: 0800c1827c636dd81e2928e33c0ee2afde4c94ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259145"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX denetimleri: Bir Metottan hata kodları döndürme

Bu makalede, bir ActiveX denetimi yöntemden hata kodları döndürme açıklar.

Bir yöntem içinde bir hata oluştuğunu göstermek için kullanmalısınız [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) bir ' % s'SCODE (durum kodu) parametre olarak alan üye işlevi. Önceden tanımlanmış SCODE kullanabilir veya kendi tanımlayın.

> [!NOTE]
>  `ThrowError` bir özelliğin Get veya Set içindeki bir hatadan döndüren yalnızca bir yol olarak kullanılmak üzere tasarlanmıştır işlev veya bir Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyicisi olacak kez yığında sunar.

Yardımcı işlevleri mevcut SCODEs, en yaygın gibi önceden tanımlanmış [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

Önceden tanımlanmış SCODEs ve özel SCODEs tanımlama yönergeleri listesi için konudaki [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.

Kodunuzun diğer alanlarda özel durumları hakkında daha fazla bilgi için bkz: [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
