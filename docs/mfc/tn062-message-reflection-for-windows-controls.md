---
description: 'Hakkında daha fazla bilgi edinin: TN062: Windows denetimleri için Ileti yansıması'
title: 'TN062: Windows Denetimleri için İleti Yansıması'
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
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
ms.openlocfilehash: 9dc106c1513032e654acfc2c4b86b8eb3b939578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214734"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Windows Denetimleri için İleti Yansıması

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu teknik notta, MFC 4,0 ' de yeni bir özellik olan ileti yansıması açıklanmaktadır. İleti yansımasını kullanan basit bir yeniden kullanılabilir denetim oluşturmaya yönelik yönergeler de içerir.

Bu teknik Not, ActiveX denetimleri (eski adıyla OLE denetimleri) için geçerli olduğu için ileti yansımasını ele almaz. Lütfen [ActiveX denetimleri: altsınıflama a Windows Control](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)makalesine bakın.

**Ileti yansıması nedir?**

Windows denetimleri, üst pencereleri sıklıkla bildirim iletileri gönderir. Örneğin, birçok denetim, üst öğenin denetimin arka planını boyamak için bir fırça sağlaması için üst öğesine bir denetim rengi bildirim iletisi (WM_CTLCOLOR veya türevlerinden birini) gönderir.

Sürüm 4,0 ' den önce Windows ve MFC 'de, ana pencere, genellikle bir iletişim kutusu, bu iletileri işlemekten sorumludur. Bu, iletinin işlenmesi için kodun üst pencerenin sınıfında olması ve bu iletiyi işlemesi gereken her sınıfta yinelenilmesi gereken anlamına gelir. Yukarıdaki durumda, özel arka planlarla denetimleri isteyen her iletişim kutusunun Denetim rengi bildirim iletisini işlemesi gerekir. Kendi arka plan rengini işleyecek bir denetim sınıfı yazılmışsa, kodu yeniden kullanmak çok daha kolay hale gelir.

MFC 4,0 ' de, eski mekanizma hala işe yarar — üst Windows, bildirim iletilerini işleyebilir. Bununla birlikte, MFC 4,0, bu bildirim iletilerinin alt denetim penceresinde veya üst pencerede ya da her ikisinde de işlenmesine izin veren "ileti yansıma" adlı bir özellik sağlayarak yeniden kullanılmasını kolaylaştırır. Denetim arka plan rengi örneğinde, artık üst öğeye bağlı kalmadan yansıtılan WM_CTLCOLOR iletisini işleyerek kendi arka plan rengini ayarlayan bir denetim sınıfı yazabilirsiniz. (İleti yansıma, Windows tarafından değil MFC tarafından uygulandığından, ileti yansımasıyla çalışmak için üst pencere sınıfının türetilmiş olması gerektiğini unutmayın `CWnd` .)

Daha eski MFC sürümleri, ileti yansımasına benzer bir şekilde, örneğin, sahibi tarafından çizilen liste kutuları (WM_DRAWITEM vb.) için sanal işlevler sağlar. Yeni ileti yansıma mekanizması genelleştirilir ve tutarlıdır.

İleti yansıtma, 4,0 öncesi MFC sürümleri için yazılmış kodla geriye dönük olarak uyumludur.

Belirli bir ileti için veya bir dizi ileti için bir işleyici sağladıysanız, ana pencerenin sınıfında, kendi işleyicinizde temel sınıf işleyicisi işlevini çağırmadığınız için yansıtılan ileti işleyicilerini aynı ileti için geçersiz kılar. Örneğin, iletişim kutusu sınıfınıza WM_CTLCOLOR işlerinizi yaptıysanız, işleme yansıtılan tüm ileti işleyicilerini geçersiz kılar.

Üst pencere sınıfınız içinde, belirli bir WM_NOTIFY iletisi veya bir dizi WM_NOTIFY iletisi için bir işleyici sağlarsanız, işleyiciniz yalnızca, bu iletileri gönderen alt denetimin aracılığıyla yansıtılan bir ileti işleyicisi yoksa çağrılacaktır `ON_NOTIFY_REFLECT()` . `ON_NOTIFY_REFLECT_EX()`İleti haritanızda kullanıyorsanız, ileti işleyiciniz ana pencerenin iletiyi işlemesini sağlayabilir veya buna izin vermeyebilir. İşleyici **yanlış** döndürürse, ileti üst öğe tarafından da işlenir, ancak **doğru** döndüren bir çağrı üst öğenin onu işlemesini izin vermez. Yansıtılan iletinin bildirim iletisinden önce işlendiğini unutmayın.

WM_NOTIFY bir ileti gönderildiğinde, denetime ilk işleme fırsatı sunulur. Yansıtılan başka herhangi bir ileti gönderilirse, üst pencere bunu işlemek için ilk şans olur ve denetim yansıtılan iletiyi alır. Bunu yapmak için, denetimin sınıf ileti eşlemesinde bir işleyici işlevi ve uygun bir giriş gerekecektir.

Yansıtılan iletiler için ileti eşleme makrosu, normal bildirimlerden biraz farklıdır: *_reflect* olağan adının sonuna eklenir. Örneğin, üst öğede WM_NOTIFY bir iletiyi işlemek için, üst öğenin ileti eşlemesindeki makro ON_NOTIFY kullanırsınız. Alt denetimdeki yansıtılan iletiyi işlemek için alt denetimin ileti eşlemesindeki ON_NOTIFY_REFLECT makrosunu kullanın. Bazı durumlarda parametreler farklılık da farklıdır. ClassWizard 'ın ileti eşleme girdilerini genellikle ekleyebileceğini ve doğru parametrelerle iskelet işlev uygulamalarına sahip olabileceğini unutmayın.

Yeni WM_NOTIFY iletisi hakkında bilgi için bkz. [TN061: ON_NOTIFY ve WM_NOTIFY iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md) .

**İleti eşleme girdileri ve yansıtılan Iletiler için Işleyici Işlev prototipleri**

Yansıtılan bir denetim bildirim iletisini işlemek için aşağıdaki tabloda listelenen ileti eşleme makrolarını ve işlev prototiplerini kullanın.

ClassWizard bu ileti eşleme girdilerini genellikle ekleyebilir ve iskelet işlev uygulamaları sağlayabilir. Yansıtılan iletiler için işleyicileri tanımlama hakkında bilgi için bkz. [yansıtılan bir ileti Için Ileti Işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) .

İleti adından yansıtılan makro adına dönüştürmek için, *on_* ve sonuna ekleyin *_reflect*. Örneğin, WM_CTLCOLOR ON_WM_CTLCOLOR_REFLECT olur. (Hangi iletilerin yansıtıldığını görmek için, aşağıdaki tabloda yer alan makro girişlerinde ters dönüştürmeyi yapın.)

Yukarıdaki kuralın üç özel durumu aşağıdaki gibidir:

- WM_COMMAND bildirimleri için makro ON_CONTROL_REFLECT.

- WM_NOTIFY yansıtımları için makro ON_NOTIFY_REFLECT.

- ON_UPDATE_COMMAND_UI yansıtımları için makro ON_UPDATE_COMMAND_UI_REFLECT.

Yukarıdaki özel durumların her birinde, Handler üye işlevinin adını belirtmeniz gerekir. Diğer durumlarda, işleyici işleviniz için standart adı kullanmanız gerekir.

İşlevlerin parametrelerinin ve dönüş değerlerinin anlamları, işlev adı *veya önüne eklenmiş* işlev adı altında belgelenmiştir. Örneğin, `CtlColor` içinde belgelenir `OnCtlColor` . Birkaç yansıtılan ileti işleyicisi, üst penceredeki benzer işleyicilerden daha az parametreye ihtiyaç duyar. Yalnızca aşağıdaki tablodaki adları, belgelerindeki biçimsel parametrelerin adlarıyla eşleştirin.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **( );**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *sonuç* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(CCmdUI** <strong>\*</strong> `pCmdUI` **);**|
|**ON_WM_CTLCOLOR_REFLECT ()**|**afx_msg HBRUSH CtlColor (CDC** <strong>\*</strong> `pDC` **, UINT** `nCtlColor` **);**|
|**ON_WM_DRAWITEM_REFLECT ()**|**afx_msg void DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT ()**|**afx_msg void MeasureItem (LPMEASUREıTEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT ()**|**afx_msg void DeleteItem (LPDELETEıTEMSTRUCT** `lpDeleteItemStruct` **);**|
|**ON_WM_COMPAREITEM_REFLECT ()**|**afx_msg Int CompareItem (LPCOMPAREıTEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT ()**|**afx_msg int chartoıtem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT ()**|**afx_msg int vkeytoıtem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT ()**|**afx_msg void HScroll (uint** `nSBCode` **, uint** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT ()**|**afx_msg void VScroll (uint** `nSBCode` **, uint** `nPos` **);**|
|**ON_WM_PARENTNOTIFY_REFLECT ()**|**afx_msg void parentnotıfy (UINT** `message` **, lParam** `lParam` **);**|

ON_NOTIFY_REFLECT ve ON_CONTROL_REFLECT makrolarında, belirli bir iletiyi işlemek için birden fazla nesneye (denetim ve onun üst öğesi gibi) izin veren çeşitlemeler vardır.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg bool** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *sonuç* **);**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg bool** `memberFxn` **( );**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>Yansıtılan Iletileri işleme: yeniden kullanılabilir denetim örneği

Bu basit örnek adlı yeniden kullanılabilir bir denetim oluşturur `CYellowEdit` . Denetim, normal bir düzenleme denetimiyle aynı şekilde çalışarak, sarı bir arka planda siyah metin görüntüler. Denetimin farklı renkleri görüntülemesine izin veren üye işlevleri eklemek kolay bir işlemdir `CYellowEdit` .

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Yeniden kullanılabilir bir denetim oluşturan örneği denemek için

1. Mevcut bir uygulamada yeni bir iletişim kutusu oluşturun. Daha fazla bilgi için bkz. [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) konusu.

   Yeniden kullanılabilir denetim geliştirmenin bir uygulamasına sahip olmanız gerekir. Kullanılacak mevcut bir uygulamanız yoksa AppWizard kullanarak iletişim tabanlı bir uygulama oluşturun.

2. Projeniz Visual C++ ' ye yüklendikten sonra, temelinde adlı yeni bir sınıf oluşturmak için ClassWizard ' ı kullanın `CYellowEdit` `CEdit` .

3. Sınıfınıza üç üye değişkeni ekleyin `CYellowEdit` . İlk ikisi, metin rengini ve arka plan rengini tutmak için *colorref* değişkenleri olacaktır. Üçüncü, `CBrush` arka planı boyamak için fırçayı tutacak bir nesne olacaktır. `CBrush`Nesnesi, fırçayı bir kez oluşturmanıza, yalnızca bundan sonra başvuruda bulunarak ve denetim yok edildiğinde fırçayı otomatik olarak yok etmenize olanak tanır `CYellowEdit` .

4. Aşağıdaki gibi, oluşturucuyu yazarak üye değişkenlerini başlatın:

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. ClassWizard kullanarak, sınıfınıza yansıtılan WM_CTLCOLOR iletisi için bir işleyici ekleyin `CYellowEdit` . İşleyebileceğinizi belirten iletiler listesindeki ileti adının önündeki eşittir işaretinin, iletinin yansıtıldığını unutmayın. Bu, [yansıtılan bir ileti Için Ileti Işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)konusunda açıklanmaktadır.

   Classıntertıon Sihirbazı sizin için aşağıdaki ileti eşleme makrosunu ve iskelet işlevini ekler:

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

6. İşlevin gövdesini aşağıdaki kodla değiştirin. Kod metin rengini, metin arka plan rengini ve denetimin geri kalanı için arka plan rengini belirtir.

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. İletişim kutusunda bir düzenleme denetimi oluşturun ve bir denetim tuşunu basılı tutarken düzenleme denetimine çift tıklayarak onu üye değişkenine ekleyin. Üye değişkeni Ekle iletişim kutusunda, değişken adını tamamlayın ve sonra değişken türü için "Cyellowedıt" kategorisini seçin. İletişim kutusunda sekme sırasını ayarlamayı unutmayın. Ayrıca, `CYellowEdit` iletişim kutusunun üst bilgi dosyasına denetim için üst bilgi dosyasını da eklediğinizden emin olun.

8. Uygulamanızı derleyin ve çalıştırın. Düzenleme denetimi sarı bir arka plana sahip olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
