---
title: 'TN062: Windows denetimleri için yansıma iletisi | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.messages
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 994095042dc473fda315b6d842d9ec9355ff3671
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055404"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Windows Denetimleri için İleti Yansıması

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu teknik Not ileti yansıması, yeni bir özellik MFC 4.0 açıklar. Ayrıca, ileti yansıması kullanan basit bir yeniden kullanılabilir denetimi oluşturma için yönergeler içerir.

Bu teknik Not (eski adı OLE denetimleri de denir) ActiveX denetimleri için geçerli olduğundan ileti yansıması ele almaz. Lütfen bkz [ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

**İleti yansıması nedir**

Windows denetimleri, sık sık üst pencerelerini bildirim iletilerini göndermek. Örneği için pek çok denetimi üst denetimin arka plan boyama için bir fırça kaynağı izin vermek için üst denetim renk bildirim iletisi (WM_CTLCOLOR veya türevleri biri) gönderin.

Windows ve MFC sürüm 4.0 önce üst pencere, iletişim kutusu genellikle, bu iletileri işlenmesinden sorumludur. Bu iletiyi işlemek için kod ana pencerenin sınıfta olması gerektiğini ve bu iletiyi işlemek için gereken her sınıfta çoğaltılacak olduğunu anlamına gelir. Yukarıdaki durumda özel arka plan denetimleriyle istediği her iletişim kutusu denetim renk bildirim iletisini işlemek gerekir. Denetim sınıfı, kendi arka plan rengi işlemek yazılabilir, kodu yeniden kullanmak çok daha kolay olacaktır.

MFC 4. 0'da, eski mekanizması hala çalışıyor — üst windows bildirim iletileri işleyebilir. Ayrıca, ancak, MFC 4.0 yeniden "yansıma message" adlı bir özellik sağlayarak kolaylaştıran alt denetimi penceresi veya üst pencere ya da hem de ele alınması bu bildirim iletileri sağlar. Denetim arka plan rengi örnekte, artık yansıtılan WM_CTLCOLOR iletisi işleyerek, kendi arka plan rengini ayarlar bir denetim sınıfı yazabilirsiniz; üst öğede güvenmek zorunda olmadan. (İleti yansıması MFC tarafından uygulandığından, Windows tarafından üst pencere sınıfını nesnesinden türetilmesi değil olduğunu unutmayın `CWnd` çalışmak ileti yansıması için.)

MFC eski sürümleri için ileti yansıması benzer bir şey sanal işlevler iletileri (WM_DRAWITEM ve benzeri) sahip tarafından çizilmiş liste kutuları gibi birkaç ileti sağlayarak yaptım. Yeni ileti yansıma genelleştirilmiş ve tutarlı mekanizmadır.

İleti yansıması 4.0 önce MFC sürümleri için yazılmış kod ile geriye dönük uyumludur.

Belirli bir ileti için bir işleyici tarafından sağlanan ya da bir dizi ana pencerenin sınıfında iletileri için onu geçersiz kılar, temel sınıf işleyici işlevi içinde kendi işleyicinizi Remove() çağırmayın sağlanan aynı ileti için ileti işleyicileri yansıtılır. Örneğin, iletişim kutusu sınıfınızda WM_CTLCOLOR işlemek, işleme tüm yansıtılan ileti işleyicileri geçersiz kılar.

Yalnızca bu iletileri gönderen alt denetimin yansımış bir ileti işleyicisini aracılığıyla sahip değilse üst pencere Sınıfınız içinde belirli bir wm_notıfy iletisi veya bir aralığı, wm_notıfy iletileri için bir işleyici sağlarsanız, işleyicinizi çağrılacak `ON_NOTIFY_REFLECT()`. Kullanırsanız `ON_NOTIFY_REFLECT_EX()` , ileti eşlemesi ileti işleyicinizi olabilir veya üst pencere iletisini işlemek izin vermeyebilir. İşleyici döndürürse **FALSE**, iletiyi de üst tarafından döndüren bir çağrı sırasında ele alınacaktır **TRUE** işlenmesi üst izin vermiyor. Yansımış bir ileti önce bildirim iletisi işlenir unutmayın.

Wm_notıfy iletisi gönderildiğinde, denetimin işlenmesi için ilk fırsat sunulur. Yansımış herhangi bir ileti gönderildiğinde üst pencere işlenmesi için ilk şansına sahiptir ve denetim yansımış bir ileti alırsınız. Bunu yapmak için bir işleyici işlevi ve denetimin sınıf ileti eşlemesi uygun bir girdi gerekir.

İleti eşleme makrosu yansımış iletiler için düzenli bildirimler için biraz farklıdır: sahip *_REFLECT* normal adının. Örneğin, üst bir wm_notıfy iletisini işlemek için ileti eşlemesi üst öğenin içinde on_notıfy makrosu kullanın. Alt denetiminde yansıtılan iletisini işlemek için alt denetimin ileti eşlemede on_notıfy_reflect makroyu kullanın. Bazı durumlarda, parametreleri de farklı olabilir. ClassWizard genellikle sizin için ileti eşlemesi girişleri ekleyebilir ve doğru parametrelere sahip iskelet işlev uygulamaları sağlamak olduğunu unutmayın.

Bkz: [TN061: on_notıfy ve wm_notıfy iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md) yeni wm_notıfy iletisi hakkında bilgi için.

**İleti eşlemesi girişleri ve yansımış iletiler için işleyici işlev prototipleri**

Yansıtılan denetimi bildirim iletisini işlemek için aşağıdaki tabloda listelenen işlev prototipleri ve ileti eşleme makroları kullanın.

ClassWizard genellikle sizin için bu ileti eşlemesi girişleri ekleyebilir ve iskelet işlev uygulamaları sağlar. Bkz: [yansımış bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) yansımış iletileri için işleyiciler tanımlama hakkında daha fazla bilgi için.

Yansıtılan makro adı ileti adından dönüştürmek için önüne ekleyin *ON_* ve ekleme *_REFLECT*. Örneğin, WM_CTLCOLOR ON_WM_CTLCOLOR_REFLECT haline gelir. (Hangi iletileri nelze reflektovat görmek için aşağıdaki tabloda makrosu girişlere karşı dönüştürme yapın.)

Üç yukarıdaki kuralının istisnalarıdır aşağıdaki gibidir:

- WM_COMMAND bildirimleri için ON_CONTROL_REFLECT makrodur.

- Wm_notıfy yansımaları için on_notıfy_reflect makrodur.

- On_update_command_uı_reflect makrosu on_update_command_uı yansımaları için var.

Her yukarıdaki özel durum işleyicisi üye işlevinin adını belirtmeniz gerekir. Diğer durumlarda, işleyici işleviniz için standart adı kullanmanız gerekir.

Anlamlara parametrelerinin ve dönüş değerleri işlevlerin işlev adı veya işlev adı ile altında belgelenen *üzerinde* etkileşimlidir. Örneğin, `CtlColor` belgelenen `OnCtlColor`. Birkaç yansıtılan ileti işleyicileri, daha az parametre bir üst penceresine benzer işleyiciler gerekir. Yalnızca aşağıdaki tabloda ad belgelerinde biçimsel parametre adları ile eşleştirin.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **();**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *sonucu* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(Ccmduı** <strong>\*</strong> `pCmdUI` **);**|
|**ON_WM_CTLCOLOR_REFLECT)**|**HBRUSH CtlColor afx_msg (CDC** <strong>\*</strong> `pDC` **, UINT** `nCtlColor` **);**|
|**ON_WM_DRAWITEM_REFLECT)**|**DrawItem afx_msg void (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT)**|**MeasureItem afx_msg void (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT)**|**afx_msg DeleteItem void (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|
|**ON_WM_COMPAREITEM_REFLECT)**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT)**|**afx_msg int CharToItem (UINT** `nKey` **, UINT** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT)**|**afx_msg int VKeyToItem (UINT** `nKey` **, UINT** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT)**|**afx_msg HScroll void (UINT** `nSBCode` **, UINT** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT)**|**afx_msg VScroll void (UINT** `nSBCode` **, UINT** `nPos` **);**|
|**ON_WM_PARENTNOTIFY_REFLECT)**|**afx_msg ParentNotify void (UINT** `message` **, LPARAM** `lParam` **);**|

On_notıfy_reflect ve ON_CONTROL_REFLECT makroları (örneğin, Denetim ve kendi üst) birden fazla nesne belirli bir ileti işlemeye izin farklılıklar vardır.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**BOOL afx_msg** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *sonucu* **);**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**BOOL afx_msg** `memberFxn` **();**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>İşleme Reflected iletileri: Yeniden kullanılabilir bir denetim örneği

Bu basit örnek olarak adlandırılan yeniden kullanılabilir bir denetim oluşturur `CYellowEdit`. Bir sarı arka planı siyah metin görüntüler denetimi aynı normal düzenleme denetimi olarak çalışır. İzin üye işlevleri eklemek kolay olurdu `CYellowEdit` farklı renkler görüntülenecek denetimi.

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Örnek denemek için yeniden kullanılabilir bir denetim oluşturur

1. Yeni iletişim kutusu içinde var olan bir uygulama oluşturun. Daha fazla bilgi için [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) konu.

   Yeniden kullanılabilir denetim geliştirmek üzere bir uygulama olmalıdır. Mevcut bir uygulamayı kullanmak için yoksa AppWizard kullanarak iletişim tabanlı bir uygulama oluşturun.

2. Visual C++'ta yüklenen projenizle ClassWizard adlı yeni bir sınıf oluşturmak için kullanın. `CYellowEdit` göre `CEdit`.

3. Üç üye değişkenleri ekleyip, `CYellowEdit` sınıfı. İlk iki olacaktır *COLORREF* metin rengi ile arka plan rengi tutması için değişkenleri. Üçüncü olacak bir `CBrush` için arka plan boyama fırça tutacak nesne. `CBrush` Nesne sağlar, bir kez, yalnızca bundan sonra başvuran fırça oluştur ve fırça otomatik olarak zaman yok etmek için `CYellowEdit` denetim yok edildiğinde.

4. Üye değişkenleri şu şekilde kurucunuzu yazarak başlatın:

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. ClassWizard, kullanarak eklemek için yansıtılmış WM_CTLCOLOR iletisi için bir işleyici, `CYellowEdit` sınıfı. Eşittir işaretinin önüne iletileri işleyebilir listesinde ileti adı, ileti yansıtılır olduğuna dikkat edin. Bu açıklanan [yansımış bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

   ClassWizard aşağıdaki ileti eşleme makrosu ve skeleton işlevi için ekler:

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. İşlev gövdesi aşağıdaki kodla değiştirin. Kod, metin rengi ve metin arka plan rengi rest denetimin arka plan rengini belirtir.

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. Sizin iletişim kutunuzda bir düzenleme denetimi oluşturun ve ardından CTRL tuşunu basılı çalışırken düzenleme denetimi çift tıklayarak bir üye değişkeni ekleme. Üye değişkeni Ekle iletişim kutusunda, değişkenin adını tamamlayın ve "Control" sonra "CYellowEdit" değişken türü için kategori seçin. İletişim kutusuna sekme sırasını ayarlama unutmayın. Ayrıca, üstbilgi dosyasını eklediğinizden emin olun `CYellowEdit` denetiminde iletişim kutusunun üst bilgi dosyası.

8. Derleyin ve çalıştırın. Düzenleme denetimi bir sarı arkaplanla görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
