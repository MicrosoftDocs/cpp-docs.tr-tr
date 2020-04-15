---
title: 'MFC ActiveX Denetimleri: Bir ActiveX Denetimine Stok Olaylar Ekleme'
ms.date: 11/04/2016
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
ms.openlocfilehash: 79cd4fc572e55c67cc5a2cfe3a00e04f2a4a7850
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364681"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX Denetimleri: Bir ActiveX Denetimine Stok Olaylar Ekleme

Stok olayları, [COleControl](../mfc/reference/colecontrol-class.md)sınıfı tarafından otomatik olarak ateşlendikleri özel olaylardan farklıdır. `COleControl`ortak eylemlerden kaynaklanan olayları yangın önceden tanımlanmış üye işlevleri içerir. Tarafından `COleControl` uygulanan bazı yaygın eylemler, denetime tek ve çift tıklamalar, klavye olayları ve fare düğmelerinin durumundaki değişiklikleri içerir. Stok olayları için olay haritası girişleri her zaman EVENT_STOCK öneki nden önce gelir.

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>Olay Ekle Sihirbazı Tarafından Desteklenen Stok Etkinlikleri

Sınıf, `COleControl` aşağıdaki tabloda listelenen on stok olayı sağlar. [Olay Ekle Sihirbazı'nı](../ide/add-event-wizard.md)kullanarak denetiminizde istediğiniz olayları belirtebilirsiniz.

### <a name="stock-events"></a>Stok Etkinlikleri

|Olay|Ateşleme fonksiyonu|Yorumlar|
|-----------|---------------------|--------------|
|Şuna tıklayın:|**void FireClick( )**|Denetim fareyi yakaladığında, **buttonup** (sol, orta veya sağ) iletisi alınır ve düğme denetim üzerinde serbest bırakılır. Bu olaydan önce stock MouseDown ve MouseUp olayları oluşur.<br /><br /> Olay haritası girişi: **EVENT_STOCK_CLICK( )**|
|Dblclick|**void FireDblClick( )**|**ButtonDBLCLK** iletisi geldiğinde Click'e benzer ancak ateşlenir.<br /><br /> Olay haritası girişi: **EVENT_STOCK_DBLCLICK( )**|
|Hata|**void FireError(***SCODE kodu* , **LPCSTR** `lpszDescription` , **UINT**`nHelpID`= 0 **)**        |ActiveX denetiminizde bir yöntem araması veya özellik erişimi kapsamı dışında bir hata oluştuğunda ateşlendi.<br /><br /> Olay haritası girişi: **EVENT_STOCK_ERROREVENT( )**|
|Keydown|**void FireKeyDown( kısa** `nChar` **, kısa**`nShiftState`**)**      |Bir `WM_SYSKEYDOWN` veya `WM_KEYDOWN` ileti alındığı zaman ateşlenir.<br /><br /> Olay haritası girişi: **EVENT_STOCK_KEYDOWN( )**|
|Keypress|**void FireKeyPress (kısa)** <strong>\*</strong> `pnChar` **)**    |İleti `WM_CHAR` alındığı zaman ateşlenir.<br /><br /> Olay haritası girişi: **EVENT_STOCK_KEYPRESS( )**|
|Keyup|**void FireKeyUp( kısa** `nChar` **, kısa**`nShiftState`**)**      |Bir `WM_SYSKEYUP` veya `WM_KEYUP` ileti alındığı zaman ateşlenir.<br /><br /> Olay haritası girişi: **EVENT_STOCK_KEYUP( )**|
|Mousedown|**void FireMouseDown( kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |Herhangi bir **BUTTONDOWN** (sol, orta veya sağ) alınırsa ateş. Bu olay ateşedilmeden hemen önce fare yakalanır.<br /><br /> Olay haritası girişi: **EVENT_STOCK_MOUSEDOWN( )**|
|Fare Taşı|**void FireMouseMove( kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |WM_MOUSEMOVE iletisi alındığı zaman ateşlenir.<br /><br /> Olay haritası girişi: **EVENT_STOCK_MOUSEMOVE( )**|
|Fare Yukarı|**void FireMouseUp( kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |Herhangi bir **BUTTONUP** (sol, orta veya sağ) alınırsa ateşlenir. Fare yakalama bu olay ateşedilmeden önce serbest bırakılır.<br /><br /> Olay haritası girişi: **EVENT_STOCK_MOUSEUP( )**|
|ReadyStateChange|**void FireReadyStateChange( )**|Alınan veri miktarı nedeniyle bir sonraki hazır duruma geçtiğinde ateşlenen.<br /><br /> Olay haritası girişi: **EVENT_STOCK_READYSTATECHANGE( )**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>Olay Ekle Sihirbazı'nı Kullanarak Stok Etkinliği Ekleme

Stok olayları eklemek, özel olaylar eklemekten daha az çalışma gerektirir, çünkü gerçek `COleControl`olayın ateşlenmesi taban sınıf tarafından otomatik olarak işlenir. Aşağıdaki yordam, [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)kullanılarak geliştirilen bir denetime bir stok olayı ekler. KeyPress adı verilen olay, bir tuşa basıldığında ve denetim etkin olduğunda ateşlenir. Bu yordam, diğer stok olayları eklemek için de kullanılabilir. KeyPress için seçili stok olay adını değiştirin.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Olay Ekle Sihirbazı'nı kullanarak KeyPress stok olayını eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, kısayol menüsünü açmak için ActiveX denetim sınıfınızı sağ tıklatın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Olay Ekle'yi**tıklatın.

   Bu, Olay Ekle Sihirbazı'nı açar.

1. Olay **Adı** açılır listesinde `KeyPress`.

1. **Son**'a tıklayın.

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>Stok Olayları için Olay Sihirbazı Değişiklikleri Ekleme

Stok olayları denetimin taban sınıfı tarafından işlenir olduğundan, Olay Ekle Sihirbazı sınıf bildirgenizi hiçbir şekilde değiştirmez. Olayı denetimin olay haritasına ekler ve 'nin . IDL dosyası. Aşağıdaki satır, denetim sınıfı uygulamasında bulunan denetimin olay haritasına eklenir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

WM_CHAR iletisi alındığı ve denetim etkin olduğunda bu kodun eklenmesi bir KeyPress olayını ateşler. KeyPress olayı, kontrol kodu içinden (örneğin,) `FireKeyPress`ateşleme işlevini arayarak başka zamanlarda da ateşlenebilir.

Olay Ekle Sihirbazı, denetimin .'nin kod satırına aşağıdaki satırı ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Bu satır, KeyPress olayını standart gönderi kimliğiyle ilişkilendirer ve konteynerin KeyPress olayını tahmin etmesini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
