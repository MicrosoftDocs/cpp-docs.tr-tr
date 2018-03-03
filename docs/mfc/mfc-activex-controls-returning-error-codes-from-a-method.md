---
title: "MFC ActiveX denetimleri: Bir yöntemden hata kodları döndürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5563153cdc5d90bc522c1f0b4edf48a8cc280755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme
Bu makalede, hata kodları bir ActiveX denetimi döndürme açıklar.  
  
 Yöntemi içinde bir hata oluştu belirtmek için kullanmanız gerekir [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) alan üye işlevi bir `SCODE` (durum kodu) bir parametre olarak. Kullanabileceğiniz önceden tanımlanmış bir `SCODE` veya kendi tanımlayın.  
  
> [!NOTE]
>  `ThrowError`bir özelliğin Get veya kümesi içinde bir hatadan döndüren yalnızca bir aracı olarak kullanılması amaçlanmıştır işlevi ya da bir Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyici olacaktır kez yığında sunar.  
  
 Yardımcı işlevleri mevcut önceden tanımlanmış en sık karşılaşılan için `SCODE`s, gibi [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Bir listesi için önceden tanımlanmış `SCODE`s ve özel tanımlama yönergeleri `SCODE`s, bölümüne bakın [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.  
  
 Diğer alanlarda kodunuzu özel durumları Raporlama ile ilgili daha fazla bilgi için bkz: [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX denetimleri: Gelişmiş Konular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

