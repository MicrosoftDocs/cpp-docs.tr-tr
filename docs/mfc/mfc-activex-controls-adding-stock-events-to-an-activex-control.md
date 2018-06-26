---
title: 'MFC ActiveX denetimleri: Bir ActiveX denetimine stok olaylar ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41445015f30eb953675f763652fb85ef3eeb857a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930793"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX Denetimleri: Bir ActiveX Denetimine Stok Olaylar Ekleme
Stok olayları otomatik olarak bir sınıf tarafından tetiklenen, özel olaylardan farklı [COleControl](../mfc/reference/colecontrol-class.md). `COleControl` Ortak eylemlerden kaynaklanan olaylarını harekete önceden tanımlanmış üye işlevlerini içerir. Bazı ortak eylemler tarafından uygulanan `COleControl` tek - ve çift - clicks denetim, klavye olayları ve değişiklik fare düğmeleri durumda içerir. Olay eşleme girişi olayları her zaman EVENT_STOCK öneki öncesinde hisse senedi için.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> Stok olayları tarafından desteklenen olay Ekleme Sihirbazı  
 `COleControl` Sınıfı, aşağıdaki tabloda listelenen on stok olaylar sağlar. İstediğiniz kullanarak denetim olayları belirtebilirsiniz [olay Ekleme Sihirbazı'nı](../ide/add-event-wizard.md).  
  
### <a name="stock-events"></a>Stok olayları  
  
|Olay|Tetikleme işlevi|Açıklamalar|  
|-----------|---------------------|--------------|  
|Şuna tıklayın|**void FireClick)**|Denetim fare herhangi yakalar çağrıldığında **BUTTONUP** (sol, Orta veya sağ) iletisi alındığında ve düğmesi üzerinde denetim serbest bırakılır. MouseUp olayları ve hisse senedi MouseDown önce bu olay oluşur.<br /><br /> Olay eşleme girişi: **event_stock_clıck)**|  
|DblClick|**void FireDblClick)**|Tıklatın benzer ancak harekete ne zaman bir **BUTTONDBLCLK** iletisi alındığında.<br /><br /> Olay eşleme girişi: **event_stock_dblclıck)**|  
|Hata|**void FireError (SCODE***scode* **, LPCSTR** `lpszDescription` **, UINT**`nHelpID`**= 0)** |Yöntem çağrısı veya özellik erişim kapsamı dışında ActiveX denetimi içinde bir hata meydana geldiğinde tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_ERROREVENT)**|  
|KeyDown|**void FireKeyDown (kısa** `nChar` **, kısa**`nShiftState`**)** |Ne zaman harekete bir `WM_SYSKEYDOWN` veya `WM_KEYDOWN` iletisi alındığında.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYDOWN)**|  
|KeyPress|**void FireKeyPress (kısa\***`pnChar`**)** |Ne zaman harekete bir `WM_CHAR` iletisi alındığında.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYPRESS)**|  
|KeyUp|**void FireKeyUp (kısa** `nChar` **, kısa**`nShiftState`**)** |Ne zaman harekete bir `WM_SYSKEYUP` veya `WM_KEYUP` iletisi alındığında.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYUP)**|  
|MouseDown|**void FireMouseDown (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)** |Varsa harekete **BUTTONDOWN** (sol, Orta veya sağ) alındığında. Bu olay tetiklenir hemen önce fare yakalanır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEDOWN)**|  
|MouseMove|**void FireMouseMove (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)** |WM_MOUSEMOVE iletisi alındığında gönderildi.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEMOVE)**|  
|MouseUp|**void FireMouseUp (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)** |Varsa harekete **BUTTONUP** (sol, Orta veya sağ) alındığında. Bu olay tetiklenir önce fare yakalama yayımlanır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEUP)**|  
|ReadyStateChange|**void FireReadyStateChange)**|Sonraki hazır durumu nedeniyle alınan veri miktarı için bir denetim geçişleri olduğunda tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_READYSTATECHANGE)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Stok olayını kullanarak ekleyerek olay Ekleme Sihirbazı  
 Stok olaylar ekleme gerektirir tetikleme gerçek olayın temel sınıfı tarafından otomatik olarak işlendiğinden özel olaylar ekleme daha az iş `COleControl`. Aşağıdaki yordamı kullanılarak geliştirilen bir denetimine stok olay ekler [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md). KeyPress adlı olay, bir tuşa ve denetim etkin olduğunda gönderir. Bu yordam, diğer stok olaylar eklemek için de kullanılabilir. KeyPress seçili stok olay adını değiştirin.  
  
#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı kullanarak KeyPress stok olay eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde ActiveX denetim sınıfınıza kısayol menüsünü açmak için sağ tıklatın.  
  
3.  Kısayol menüsünden tıklatın **Ekle** ve ardından **olay Ekle**.  
  
     Olay Ekleme Sihirbazı'nı açar.  
  
4.  İçinde **olay adı** aşağı açılan listesinden, `KeyPress`.  
  
5.  **Son**'a tıklayın.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> Olay Sihirbazı değişiklikleri için stok olaylar ekleme  
 Olay Ekleme Sihirbazı'nı stok olaylar denetimin temel sınıfı tarafından işlenen çünkü sınıf bildiriminize herhangi bir şekilde değiştirmez. Bir giriş yapar ve olay denetimin olay eşlemesi ekler. IDL dosyası. Denetim sınıfı uygulamasında bulunan denetimin olay eşlemesi, aşağıdaki satırı eklenir (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 Bu kod ekleme WM_CHAR iletisi aldı ve denetim etkin olduğunda tuş basışı olayı ateşlenir. KeyPress olayı diğer saatlerde tetikleme işlevini çağırarak harekete (örneğin, `FireKeyPress`) gelen denetim kodu içinde.  
  
 Olay Ekleme Sihirbazı'nı aşağıdaki kod satırını denetimin ekler. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 Bu satırı KeyPress olayı kendi standart dağıtım kimliği ile ilişkilendirir ve kapsayıcının KeyPress olayı düşündüğünüz izin verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
