---
title: "MFC ActiveX denetimleri: Stok Özellikler ekleme | Microsoft Docs"
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
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed6fec6c878fe505b18a39df1200117f4b426878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX Denetimleri: Stok Özellikler Ekleme
Stok özellikleri içeren zaten bir sınıf tarafından uygulanan özel özelliklerinden farklı `COleControl`. `COleControl`Ortak Özellikler Denetim için destek önceden tanımlanmış üye işlevlerini içerir. Denetimin başlığı ve ön ve arka plan renkleri bazı ortak özellikleri içerir. Diğer stok özellikleri hakkında daha fazla bilgi için bkz: [hisse senedi özellikleri Özellik Ekleme Sihirbazı'nı tarafından desteklenen](#_core_stock_properties_supported_by_classwizard) bu makalenin ilerisinde yer. Stok özellikleri için gönderme eşleme girdilerini her zaman tarafından önek **DISP_STOCKPROP**.  
  
 Bu makalede, Özellik Ekleme Sihirbazı'nı kullanarak bir ActiveX denetimine stok özellik (Bu durumda, resim yazısı) eklemeyi açıklar ve sonuçta elde edilen bir kod değişikliği açıklar. Konular şunlardır:  
  
-   [Stok özellik eklemek için Özellik Ekleme Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [Stok özellikleri için özellik Sihirbazı değişiklikleri Ekle](#_core_classwizard_changes_for_stock_properties)  
  
-   [Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri](#_core_stock_properties_supported_by_classwizard)  
  
-   [Stok özellikleri ve bildirim](#_core_stock_properties_and_notification)  
  
-   [Renk özellikleri](#_core_color_properties)  
  
    > [!NOTE]
    >  Visual Basic özel denetimler genellikle üst, sol, genişlik, yükseklik, Hizala, etiket, ad, tabIndex, TabStop ve üst gibi özelliklere sahiptir. ActiveX denetimi kapsayıcıları, ancak bu denetim özellikleri uygulamak için sorumlu ve bu nedenle ActiveX denetimlerini bu özellikleri desteklemiyor.  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a>Kullanarak stok özellik eklemek için özellik Sihirbazı Ekle  
 Stok Özellikler ekleme, çünkü özel özellikler ekleme daha az kod gerektirir özelliği tarafından otomatik olarak işlenen desteği `COleControl`. Aşağıdaki yordam bir ActiveX denetimi çerçeve resim yazısı özelliğini stok ekleme gösterir ve stok diğer özellikleri eklemek için de kullanılabilir. Seçili stok özellik adı resim yazısı yerine koyun.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok resim yazısı özelliğini eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).  
  
5.  İçinde **özellik adı** kutusunda, **resim yazısı**.  
  
6.  **Son**'a tıklayın.  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a>Stok özellikleri için özellik Sihirbazı değişiklikleri Ekle  
 Çünkü `COleControl` destekler stok özellikleri, Özellik Ekleme Sihirbazı'nı herhangi bir şekilde sınıf bildirimi değiştirmez; gönderme eşlemeye özelliği ekler. Özellik Ekleme Sihirbazı'nı uygulamasında bulunan denetimi gönderme haritasını aşağıdaki satırı ekler (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]  
  
 Aşağıdaki satırı denetiminizin arabirim açıklaması eklenir (. IDL) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]  
  
 Bu satırı resim yazısı özelliğini belirli bir kimliği atar. Özellik bağlanabilir ve izni değeri değiştirmeden önce veritabanından isteyecek dikkat edin.  
  
 Bu resim yazısı özelliğini denetiminizi kullanıcılara kullanılabilmesini sağlar. Stok özellik değerini kullanmak için bir üye değişkeni veya üye işlevini erişimi `COleControl` temel sınıfı. Bu üye değişkenleri ve üye işlevleri hakkında daha fazla bilgi için sonraki bölümde hisse senedi özellikleri Özellik Ekleme Sihirbazı'nı tarafından desteklenen bakın.  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a>Hisse senedi tarafından desteklenen özellikler ekleme özelliği Sihirbazı  
 `COleControl` Sınıfı dokuz stok özellikleri sağlar. Özellik Ekleme Sihirbazı'nı kullanarak istediğiniz özellikleri ekleyebilirsiniz.  
  
|Özellik|Gönderme eşleme girişi|Değer erişme|  
|--------------|------------------------|-------------------------|  
|**Görünüm**|**DISP_STOCKPROP_APPEARANCE)**|Değer olarak erişilebilir **m_sAppearance**.|  
|`BackColor`|**DISP_STOCKPROP_BACKCOLOR)**|Değer çağırarak erişilebilir `GetBackColor`.|  
|`BorderStyle`|**DISP_STOCKPROP_BORDERSTYLE)**|Değer olarak erişilebilir **m_sBorderStyle**.|  
|**Açıklamalı alt yazı**|**DISP_STOCKPROP_CAPTION)**|Değer çağırarak erişilebilir `InternalGetText`.|  
|**Etkin**|**DISP_STOCKPROP_ENABLED)**|Değer olarak erişilebilir **m_bEnabled**.|  
|**Yazı tipi**|**DISP_STOCKPROP_FONT)**|Makalesine bakın [MFC ActiveX denetimleri: yazı tiplerini kullanarak](../mfc/mfc-activex-controls-using-fonts.md) kullanım için.|  
|`ForeColor`|**DISP_STOCKPROP_FORECOLOR)**|Değer çağırarak erişilebilir `GetForeColor`.|  
|**hWnd**|**DISP_STOCKPROP_HWND)**|Değer olarak erişilebilir `m_hWnd`.|  
|**Metin**|**DISP_STOCKPROP_TEXT)**|Değer çağırarak erişilebilir `InternalGetText`. Bu özellik aynıdır **resim yazısı**, özellik adı dışında.|  
|**ReadyState**|**DISP_STOCKPROP_READYSTATE()**|Değer m_lReadyState erişilebilir veya`GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a>Stok özellikleri ve bildirim  
 Geçersiz kılınabilir bildirim işlevleri çoğu stok özellikleri vardır. Örneğin, her `BackColor` özelliği değiştirildiğinde, `OnBackColorChanged` işlevi (Denetim sınıfının üye işlevini) çağrılır. Varsayılan uygulama (içinde `COleControl`) çağrıları `InvalidateControl`. Bu durum yanıta ek eylemleri uygulamak istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="_core_color_properties"></a>Renk özellikleri  
 Hisse senedi kullanabilirsiniz `ForeColor` ve `BackColor` özellikleri veya denetim boyama yaparken, kendi özel renk özellikleri. Bir renk özelliğini kullanmak için arama [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) üye işlevi. Bu işlev color özelliği ve bir isteğe bağlı palet tanıtıcısı değerini parametreleridir. Dönüş değeri bir **COLORREF** gibi GDI için geçirilen değer işlevlerini `SetTextColor` ve `CreateSolidBrush`.  
  
 Hisse senedi renk değerleri `ForeColor` ve `BackColor` özellikleri ya da çağırarak erişilir `GetForeColor` veya `GetBackColor` sırasıyla işlev.  
  
 Aşağıdaki örnek, bir denetim boyama yaparken bu iki renk özellikleri kullanarak gösterir. Geçici bir başlatır **COLORREF** değişken ve `CBrush` çağrıları nesnesiyle `TranslateColor`: kullanarak bir tane `ForeColor` özelliği ve diğer kullanma `BackColor` özelliği. Geçici bir `CBrush` nesne denetimin dikdörtgeni boyamak için kullanılan sonra ve metin rengi kullanılarak ayarlanan `ForeColor` özelliği.  
  
 [!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
