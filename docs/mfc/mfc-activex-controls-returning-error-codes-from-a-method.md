---
title: "MFC ActiveX denetimleri: Bir yöntemden hata kodları döndürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 878d31d779d6722f25e9a3b53847cea25daac6e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

