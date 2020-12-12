---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: bir ActiveX denetimine hisse senedi olayları ekleme'
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
ms.openlocfilehash: e5b99ca2cd8675ab133f56d0e815abe0829867eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202905"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX Denetimleri: Bir ActiveX Denetimine Stok Olaylar Ekleme

Hisse senedi olayları, sınıf [Coelcontrol](reference/colecontrol-class.md)tarafından otomatik olarak tetiklendikleri için özel olaylardan farklıdır. `COleControl` ortak eylemlerden kaynaklanan olayları harekete gerçekleştiren önceden tanımlanmış üye işlevlerini içerir. Tarafından uygulanan bazı yaygın eylemler, `COleControl` Denetim, klavye olayları ve fare düğmelerinin durumundaki değişiklikler için tek ve çift tıklamaları içerir. Stok olayları için olay eşlemesi girişleri her zaman EVENT_STOCK ön eki tarafından yapılır.

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a> Olay Ekleme Sihirbazı tarafından desteklenen stok olayları

`COleControl`Sınıfı, aşağıdaki tabloda listelenen on stok olayı sağlar. Denetim içinde istediğiniz olayları [olay Ekleme Sihirbazı](../ide/adding-an-event-visual-cpp.md#add-event-wizard)' nı kullanarak belirtebilirsiniz.

### <a name="stock-events"></a>Stok etkinlikleri

|Olay|Tetikleme işlevi|Yorumlar|
|-----------|---------------------|--------------|
|Eski kimlik doğrulamasını engelleme hakkında daha fazla bilgi edinmek için|**void FireClick ()**|Denetim fareyi yakaladığında harekete geçirilir, tüm **buttonup** (sol, orta veya sağ) ileti alınır ve düğme denetim üzerinden serbest bırakılır. Stock MouseDown ve MouseUp olayları bu olaydan önce oluşur.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_CLICK ()**|
|DblClick|**void FireDblClick ()**|Düğmeye benzer ancak bir **buttondblclk** iletisi alındığında harekete geçirilir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_DBLCLICK ()**|
|Hata|**void FireError (SCODE***SCODE* **, LPCSTR** `lpszDescription` **, UINT** `nHelpID` **= 0)**        |Bir yöntem çağrısının veya özellik erişiminin kapsamı dışında ActiveX denetimide bir hata oluştuğunda tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_ERROREVENT ()**|
|KeyDown|**void firekeydown (kısa** `nChar` **, kısa** `nShiftState` **)**      |Bir `WM_SYSKEYDOWN` veya `WM_KEYDOWN` iletisi alındığında tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYDOWN ()**|
|KeyPress|**void FireKeyPress (kısa** <strong>\*</strong> `pnChar` **)**    |`WM_CHAR`İleti alındığında harekete geçirildi.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYPRESS ()**|
|KeyUp|**void firekeyup (kısa** `nChar` **, kısa** `nShiftState` **)**      |Bir `WM_SYSKEYUP` veya `WM_KEYUP` iletisi alındığında tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_KEYUP ()**|
|MouseDown|**void firemouseazaltma (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |Herhangi bir **Buttonazaltma** (sol, orta veya sağ) alınmışsa tetiklenir. Fare bu olay tetiklenmadan hemen önce yakalanır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEDOWN ()**|
|Olayına|**void firemousemove (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |WM_MOUSEMOVE bir ileti alındığında harekete geçirilir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEMOVE ()**|
|Dan|**void firemouseup (kısa** `nButton` **, kısa** `nShiftState` **, float***x* **, float***y***)**          |Herhangi bir **buttonup** (sol, orta veya sağ) alınmışsa harekete geçirilir. Fare yakalama, bu olay tetiklenmadan önce serbest bırakılır.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_MOUSEUP ()**|
|ReadyStateChange|**void Firereadrivstatechange ()**|Bir denetim, alınan veri miktarı nedeniyle bir sonraki hazırlık durumuna geçerse tetiklenir.<br /><br /> Olay eşleme girişi: **EVENT_STOCK_READYSTATECHANGE ()**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a> Olay Ekleme Sihirbazı 'Nı kullanarak stok olayı ekleme

Gerçek olay, temel sınıf tarafından otomatik olarak işlendiğinden, stok olaylarının eklenmesi özel olaylar eklemekten daha az iş gerektirir `COleControl` . Aşağıdaki yordam, [MFC ActiveX Denetim Sihirbazı](reference/mfc-activex-control-wizard.md)kullanılarak geliştirilen bir denetime hisse senedi olayı ekler. Tuşa basıldığında ve denetim etkin olduğunda, KeyPress olarak adlandırılan olay ateşlenir. Bu yordam, diğer stok olaylarını eklemek için de kullanılabilir. Seçili hisse senedi olay adını KeyPress için değiştirin.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı 'nı kullanarak KeyPress stoku olayını eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü menüsünde, ActiveX denetim sınıfınızı sağ tıklayıp kısayol menüsünü açın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **olay Ekle**' ye tıklayın.

   Bu, olay Ekleme Sihirbazı ' nı açar.

1. **Olay adı** açılır listesinde, öğesini seçin `KeyPress` .

1. **Finish (Son)** düğmesine tıklayın.

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a> Stok olayları için olay Sihirbazı değişiklikleri ekleme

Stok olayları denetimin temel sınıfı tarafından işlendiği için, olay Ekle Sihirbazı sınıf bildiriinizi hiçbir şekilde değiştirmez. Olayı denetimin olay haritasına ekler ve içinde bir giriş yapar. IDL dosyası. Denetim sınıfı uygulamasında bulunan denetimin olay haritasına aşağıdaki satır eklenir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#5](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Bu kodu eklemek WM_CHAR bir ileti alındığında ve denetim etkin olduğunda bir KeyPress olayı tetikler. KeyPress olayı, Denetim kodunun içinden tetikleme işlevi (örneğin,) çağırarak diğer zamanlarda tetiklenebilir `FireKeyPress` .

Olay Ekleme Sihirbazı, aşağıdaki kod satırını denetim 'e ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#6](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Bu satır, KeyPress olayını standart gönderme KIMLIĞIYLE ilişkilendirir ve kapsayıcının KeyPress olayını tahmin etmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
