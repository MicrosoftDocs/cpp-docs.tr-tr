---
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
ms.openlocfilehash: 5314545a3a903158362dbfa65c4a9a1b2143e86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364555"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme

Bu makalede, activex denetim yönteminden hata kodlarının nasıl döndürülecekleri açıklanmaktadır.

Bir yöntem içinde bir hata oluştuğunu belirtmek için [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) üye işlevini kullanmanız gerekir ve bu işlev parametre olarak Bir SCODE (durum kodu) alır. Önceden tanımlanmış bir SCODE kullanabilir veya kendi kodunuzu tanımlayabilirsiniz.

> [!NOTE]
> `ThrowError`yalnızca bir mülkün Get or Set işlevi veya otomasyon Yöntemi'nden bir hatayı döndürmek için kullanılır. Bunlar, yığında uygun özel durum işleyicisinin bulunacağı tek zamanlardır.

Yardımcı işlevler [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)ve [COleControl::SetNotAllowed](../mfc/reference/colecontrol-class.md#setnotpermitted)gibi en yaygın önceden tanımlanmış SCODEs için var .

Önceden tanımlanmış SCOD'ların listesi ve özel SCOD'ların tanımlanmasıyla ilgili talimatlar için [ActiveX Denetiminizde ActiveX Denetiminizdeki Hataları İşleme](../mfc/mfc-activex-controls-advanced-topics.md) bölümüne bakın: Gelişmiş Konular.

Kodunuzu diğer alanlardaki özel durumları raporlama hakkında daha fazla bilgi için [Bkz.](../mfc/reference/colecontrol-class.md#fireerror) [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
