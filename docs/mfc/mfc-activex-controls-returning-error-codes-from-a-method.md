---
title: 'MFC ActiveX denetimleri: Bir Metottan hata kodları döndürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9daaa86f6f57d28b56a7374ff64b0fcbca2a3d98
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383603"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme

Bu makalede, bir ActiveX denetimi yöntemden hata kodları döndürme açıklar.

Bir yöntem içinde bir hata oluştuğunu göstermek için kullanmalısınız [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) bir ' % s'SCODE (durum kodu) parametre olarak alan üye işlevi. Önceden tanımlanmış SCODE kullanabilir veya kendi tanımlayın.

> [!NOTE]
>  `ThrowError` bir özelliğin Get veya Set içindeki bir hatadan döndüren yalnızca bir yol olarak kullanılmak üzere tasarlanmıştır işlev veya bir Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyicisi olacak kez yığında sunar.

Yardımcı işlevleri mevcut SCODEs, en yaygın gibi önceden tanımlanmış [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

Önceden tanımlanmış SCODEs ve özel SCODEs tanımlama yönergeleri listesi için konudaki [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.

Kodunuzun diğer alanlarda özel durumları hakkında daha fazla bilgi için bkz: [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

