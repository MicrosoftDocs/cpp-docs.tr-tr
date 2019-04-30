---
title: 'MFC ActiveX denetimleri: Bir ActiveX denetimine stok olaylar ekleme'
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
ms.openlocfilehash: 9f6f3c63f0436296791df428c704bce96eca3ec0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392732"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX denetimleri: Bir ActiveX denetimine stok olaylar ekleme

Stok olaylar farklı özel olayları otomatik olarak bir sınıf tarafından tetiklenen, [COleControl](../mfc/reference/colecontrol-class.md). `COleControl` Ortak Eylemler kaynaklanan olayları tetiklemesine önceden tanımlanmış üye işlevleri içerir. Bazı ortak eylemler tarafından uygulanan `COleControl` tek - ve çift - clicks denetim, klavye olaylarını ve değişiklikleri fare düğmesi durumunda içerir. Olay eşleme girişi olayları her zaman EVENT_STOCK öneki tarafından öncelenen hisse senedi için.

##  <a name="_core_stock_events_supported_by_classwizard"></a> Stok olayları tarafından desteklenen olay Ekleme Sihirbazı

`COleControl` Sınıfı aşağıdaki tabloda listelenen on stok olayları sağlar. İstediğiniz kullanarak denetim olayları belirlediğiniz [olay Ekleme Sihirbazı'nı](../ide/add-event-wizard.md).

### <a name="stock-events"></a>Stok olayları

|Olay|Tetikleme işlevi|Açıklamalar|
|-----------|---------------------|--------------|
|Şuna tıklayın|**void FireClick)**|Denetim her fareyi yakaladığında harekete **BUTTONUP** (sol, Orta veya sağ) ileti alındığında ve düğmesi denetimin üzerine serbest bırakıldığında. MouseUp olayları ve stok MouseDown önce bu olayı oluşur.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_CLICK( )**|
|DblClick|**void FireDblClick)**|Tıkla benzer ancak harekete ne zaman bir **BUTTONDBLCLK** iletisi aldı.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_DBLCLICK( )**|
|Hata|**FireError void (SCODE***scode* **, LPCSTR** `lpszDescription` **, UINT**`nHelpID`**= 0)**|Bir yöntem çağrısı veya özellik erişim kapsamı dışında ActiveX denetimi içinde bir hata meydana geldiğinde tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_ERROREVENT)**|
|KeyDown|**void FireKeyDown (kısa** `nChar` **, kısa**`nShiftState`**)**|Ne zaman tetiklenen bir `WM_SYSKEYDOWN` veya `WM_KEYDOWN` iletisi alındığında.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYDOWN( )**|
|Tuş Basışı|**void FireKeyPress (kısa** <strong>\*</strong> `pnChar` **)**|Ne zaman tetiklenen bir `WM_CHAR` iletisi aldı.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYPRESS( )**|
|KeyUp|**void FireKeyUp (kısa** `nChar` **, kısa**`nShiftState`**)**|Ne zaman tetiklenen bir `WM_SYSKEYUP` veya `WM_KEYUP` iletisi alındığında.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYUP( )**|
|MouseDown|**void FireMouseDown (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)**|Varsa harekete **BUTTONDOWN** (sol, Orta veya sağ) alındığında. Bu olay harekete hemen geçirilmeden önce fare yakalanır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEDOWN( )**|
|MouseMove|**void FireMouseMove (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)**|WM_MOUSEMOVE iletisi alındığında tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEMOVE)**|
|MouseUp|**void FireMouseUp (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float** *y***)**|Varsa harekete **BUTTONUP** (sol, Orta veya sağ) alındığında. Bu olay harekete önce fare yakalama serbest bırakılır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEUP)**|
|ReadyStateChange|**void FireReadyStateChange)**|Denetim geçişlerinden sonraki hazır duruma alınan veri miktarı nedeniyle başlatıldı.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_READYSTATECHANGE( )**|

##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Kullanarak stok olayı ekleme olay Ekleme Sihirbazı

Stok olaylar ekleme, gerçek olayın Açmadığınızda taban sınıfı tarafından otomatik olarak ele alındığından, özel olaylar ekleme değerinden daha az çalışma gerektirir `COleControl`. Aşağıdaki yordam kullanılarak geliştirilmiş bir denetim için stok olayı ekler [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md). KeyPress adlı olay, bir tuşa basıldığında ve denetim etkin olduğunda başlatılır. Bu yordam, diğer stok olaylar ekleme için de kullanılabilir. Seçili stok olayı tuş basışı ile değiştirin.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı kullanarak tuş basışı stok olayı eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde sağ tıklayın, ActiveX denetim sınıfı kısayol menüsünü açın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **olay Ekle**.

   Bu olay Ekleme Sihirbazı'nı açar.

1. İçinde **olay adı** aşağı açılan listesinden `KeyPress`.

1. **Son**'a tıklayın.

##  <a name="_core_classwizard_changes_for_stock_events"></a> Olay Sihirbazı değişiklikler için stok olaylar ekleme

Stok olaylar denetimin taban sınıfı tarafından işlenir, çünkü olay Ekleme Sihirbazı'nı sınıf bildiriminizin hiçbir şekilde değiştirmez. Denetimin olay eşlemesi için olay ekler ve bir giriş sağlar. IDL dosyası. Denetim sınıfı uygulaması içinde bulunan, denetimin olay eşlemesi aşağıdaki satırı eklenir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Bu kod ekleme WM_CHAR mesajı alındı ve denetim etkin tuş basışı olayı tetikler. KeyPress olayı diğer zamanlarda Açmadığınızda işlevini çağırarak harekete (örneğin, `FireKeyPress`) gelen denetim kodu içinde.

Olay Ekleme Sihirbazı'nı aşağıdaki kod satırını denetimin ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Bu satır, tuş basışı olayını kendi standart dağıtım kimliği ile ilişkilendirir ve kapsayıcının tuş basışı olayını tahmin izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
