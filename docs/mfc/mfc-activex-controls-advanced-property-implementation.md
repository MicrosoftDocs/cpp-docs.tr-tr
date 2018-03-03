---
title: "MFC ActiveX denetimleri: Gelişmiş özellik uygulama | Microsoft Docs"
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
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ac8b2cb1a9c8de43ecfbd2f4712d19750bb143a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama
Bu makalede bir ActiveX denetimini özelliklerinde Gelişmiş uygulama için ilgili konular açıklanmaktadır:  
  
-   [Salt okunur ve salt yazılır Özellikler](#_core_read2donly_and_write2donly_properties)  
  
-   [Bir özellikten hata kodları döndürme](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a>Salt okunur ve salt yazılır Özellikler  
 Özellik Ekleme Sihirbazı'nı denetimi için salt okunur veya salt yazılır özellikler uygulamak için hızlı ve kolay bir yöntem sağlar.  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>Bir salt okunur veya sadece yazılabilir özelliği uygulamak için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).  
  
5.  İçinde **özellik adı** , özelliğin adını yazın.  
  
6.  İçin **uygulama türü**, tıklatın **Get/Set yöntemleri**.  
  
7.  İçinde **özellik türü** kutusunda, uygun türde bir özellik için seçin.  
  
8.  Salt okunur bir özellik kümesi işlevi adı temizleyin. Salt yazılır özellik Get işlev adı temizleyin.  
  
9. **Son**'a tıklayın.  
  
 Bunu yaptığınızda, Özellik Ekleme Sihirbazı'nı işlevi ekler `SetNotSupported` veya `GetNotSupported` normal yerine gönderme eşleme girişi ayarlayın veya alın işlevi.  
  
 Salt okunur veya sadece yazılabilir olması için var olan bir özelliği değiştirmek istiyorsanız, gönderme harita el ile düzenleyin ve denetim sınıfından gereksiz kümesi veya Get işlevi kaldırın.  
  
 Koşullu salt okunur veya salt okunur (örneğin, yalnızca belirli bir modda denetiminizi çalışırken) için özellik istiyorsanız, normal, ayarlama veya Get işlevi sağlar ve arama `SetNotSupported` veya `GetNotSupported` uygun olan yerlerde işlev. Örneğin:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 Bu kod örneği çağırır `SetNotSupported` varsa `m_bReadOnlyMode` veri üyesi olduğu **doğru**. Varsa **yanlış**, özelliği yeni değere ayarlanır.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a>Bir özellikten hata kodları döndürme  
 Get veya bir özellik Ayarla çalışılırken bir hata oluştu belirtmek için kullanın `COleControl::ThrowError` geçen işlevi bir `SCODE` (durum kodu) bir parametre olarak. Kullanabileceğiniz önceden tanımlanmış bir `SCODE` veya kendi tanımlayın. Bir listesi için önceden tanımlanmış `SCODE`s ve özel tanımlamaya yönelik yönergeler `SCODE`s, bkz: [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) makale ActiveX denetimleri: Gelişmiş Konular.  
  
 Yardımcı işlevleri mevcut önceden tanımlanmış en sık karşılaşılan için `SCODE`s, gibi [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError`bir özelliğin Get veya kümesi içinde bir hatadan döndüren yalnızca bir aracı olarak kullanılması amaçlanmıştır işlevi ya da bir Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyici olacaktır kez yığında sunar.  
  
 Diğer alanlarda özel durum kodunun raporlama ile ilgili daha fazla bilgi için bkz: [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) makalede ActiveX denetimleri: Gelişmiş Konular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
