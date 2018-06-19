---
title: 'MFC ActiveX denetimleri: Bir yöntemden hata kodları döndürme | Microsoft Docs'
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
ms.openlocfilehash: 43bf6730cf1b914405f99af6572a0a53cd942ac6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354825"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme
Bu makalede, hata kodları bir ActiveX denetimi döndürme açıklar.  
  
 Yöntemi içinde bir hata oluştu belirtmek için kullanmanız gerekir [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) alan üye işlevi bir `SCODE` (durum kodu) bir parametre olarak. Kullanabileceğiniz önceden tanımlanmış bir `SCODE` veya kendi tanımlayın.  
  
> [!NOTE]
>  `ThrowError` bir özelliğin Get veya kümesi içinde bir hatadan döndüren yalnızca bir aracı olarak kullanılması amaçlanmıştır işlevi ya da bir Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyici olacaktır kez yığında sunar.  
  
 Yardımcı işlevleri mevcut önceden tanımlanmış en sık karşılaşılan için `SCODE`s, gibi [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Bir listesi için önceden tanımlanmış `SCODE`s ve özel tanımlama yönergeleri `SCODE`s, bölümüne bakın [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.  
  
 Diğer alanlarda kodunuzu özel durumları Raporlama ile ilgili daha fazla bilgi için bkz: [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

