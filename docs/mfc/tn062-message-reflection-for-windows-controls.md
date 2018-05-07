---
title: 'TN062: Windows denetimleri için yansıması ileti | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ba8e9cac3b7f7997da8c620966234a630b9b9fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Windows Denetimleri için İleti Yansıması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu teknik Not ileti yansıması, MFC 4.0 yeni bir özellik açıklanmaktadır. İleti yansıması kullanan basit bir yeniden kullanılabilir denetimi oluşturmak için yönergeleri de içerir.  
  
 ActiveX denetimleri (eski adıyla OLE denetimleri) için geçerli olduğundan, bu Teknik Not ileti yansıması açıklanmamıştır. Lütfen makalesine bakın [ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 **İleti yansıması nedir**  
  
 Windows denetimleri sık kendi üst windows bildirim iletilerini göndermek. Örneğin, birçok denetimleri bir denetim renk bildirim iletisini göndermek (`WM_CTLCOLOR` veya türevleri) kendi üst denetimin arka plan boyama için fırça sağlamak üst izin vermek için.  
  
 Windows ve MFC önce sürüm 4. 0'de, üst pencere, iletişim kutusu genellikle, bu iletiler işlemekten sorumludur. Bu iletiyi işlemek için kod üst pencerenin sınıfta olması gerektiğini ve bu iletiyi işlemek için gereken her sınıfında çoğaltılacak olduğunu anlamına gelir. Yukarıdaki durumda özel arka planlar denetimleriyle istediği her iletişim kutusu denetim renk bildirim iletisi işlemek gerekir. Denetim sınıfı kendi arka plan rengi işleyen yazılabilir varsa kodu tekrar çok daha kolay olacaktır.  
  
 MFC 4. 0'da, eski mekanizması çalışmaya devam ettiğinden — üst windows bildirim iletilerini işleyebilir. Ayrıca, ancak, MFC 4.0 yeniden "yansıma iletisi" adlı bir özelliği sağlayarak kolaylaştıran alt denetim penceresinde veya üst pencere ya da hem de işlenecek bu bildirim iletilerini sağlar. Denetim arka plan rengi örnekte yansıtılan işleyerek kendi arka plan rengini ayarlar control sınıfı şimdi yazabilirsiniz `WM_CTLCOLOR` ileti — üst öğede bağlı olan tüm olmadan. (İleti yansıması MFC tarafından uygulandığından, Windows tarafından üst pencere sınıfı öğesinden türetilmelidir değil, Not `CWnd` çalışmak ileti yansıması için.)  
  
 MFC eski sürümleri vermedi şuna benzer bir ileti yansıması sahip tarafından çizilmiş liste kutuları için iletileri gibi birkaç iletileri sanal işlevleri sağlayarak (`WM_DRAWITEM`, vb.). Yeni ileti yansıma genelleştirilmiş ve tutarlı mekanizmadır.  
  
 İleti yansıması 4.0 önce MFC sürümleri için yazılmış kod ile geriye dönük uyumludur.  
  
 Kendi işleyicisinde taban sınıfı işleyici işlevi çağrısı yok sağlanan, belirli bir ileti için bir işleyici sağladığınız veya iletilerinde üst pencerenin sınıfı, bir dizi için bunu geçersiz kılar, aynı ileti için ileti işleyicileri yansıtılır. Örneğin, işleme, `WM_CTLCOLOR` iletişim kutusu sınıfınızda, işleme tüm yansıtılan ileti işleyicileri geçersiz kılar.  
  
 Üst pencere sınıfı içinde belirli bir işleyici sağlarsanız, **wm_notıfy** ileti veya bir dizi **wm_notıfy** ileti işleyicinizi çağrılır yalnızca bu iletileri gönderen alt denetim varsa Yansıtılan ileti işleyicisi aracılığıyla sahip değilse **ON_NOTIFY_REFLECT()**. Kullanırsanız **ON_NOTIFY_REFLECT_EX()** , ileti eşlemesi ileti işleyicinizi olabilir veya iletiyi işlemek üst pencere izin vermeyebilir. İşleyici döndürürse **FALSE**, ileti döndüren bir çağrı sırasında de üst tarafından işlenecek **TRUE** işlenmesi üst izin vermiyor. Yansıtılan ileti önce bildirim iletisi işlenir unutmayın.  
  
 Zaman bir **wm_notıfy** iletinin gönderildiği, Denetim işlenmesi için ilk fırsat sunulur. Yansıtılan herhangi bir iletisi gönderirse işlenmesi için ilk fırsat üst pencere var ve denetim yansıtılan iletisi alırsınız. Bunu yapmak için bir işleyici işlevi ve uygun bir girdi denetimin sınıf ileti eşlemesi de gerekir.  
  
 Yansımış iletiler için ileti eşlemesi makrosu düzenli bildirimler için biraz farklıdır: sahip **_REFLECT** normal adını eklenir. Örneğin, işlemek için bir **wm_notıfy** ileti makrosu kullanın, üst `ON_NOTIFY` üst öğenin ileti eşlemesi içinde. Alt denetim yansıtılan iletisinde işlemek için kullanmak **on_notıfy_reflect** makro alt denetimin ileti eşlemesi içinde. Bazı durumlarda, parametreleri de farklı olabilir. ClassWizard genellikle sizin için ileti eşlemesi girişleri ekleyebilir ve doğru parametrelerle iskelet işlevi uygulamalarını olduğunu unutmayın.  
  
 Bkz: [TN061: on_notıfy ve wm_notıfy iletileri](../mfc/tn061-on-notify-and-wm-notify-messages.md) yeni hakkında bilgi için **wm_notıfy** ileti.  
  
 **İleti eşleme girişi ve yansımış iletiler için işleyici işlev prototipleri**  
  
 Yansıtılan denetim bildirim iletisi işlemek için aşağıdaki tabloda listelenen işlev prototipleri ve ileti eşleme makroları kullanın.  
  
 ClassWizard genellikle bu ileti eşleme girişleri eklediğiniz ve iskelet işlevi uygulamaları sağlar. Bkz: [yansıtılan bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) yansımış iletileri için işleyiciler tanımlayın hakkında bilgi için.  
  
 Yansıtılan makrosu adına ileti adından dönüştürmek için başına **ON_** ve ilave **_REFLECT**. Örneğin, `WM_CTLCOLOR` hale **ON_WM_CTLCOLOR_REFLECT**. (Hangi iletilerin yansıtılan görmek için aşağıdaki tabloda makrosu girdileri ters dönüştürme yapılamıyor.)  
  
 Yukarıda kural üç istisnaları aşağıdaki gibidir:  
  
-   Makro **WM_COMMAND** bildirimleri olan **ON_CONTROL_REFLECT**.  
  
-   Makro **wm_notıfy** yansımaları olan **on_notıfy_reflect**.  
  
-   Makro `ON_UPDATE_COMMAND_UI` yansımaları olan **on_update_command_uı_reflect**.  
  
 Her yukarıdaki özel durumlar, işleyici üye işlevin adını belirtmeniz gerekir. Diğer durumlarda, işleyici işlevi için standart adı kullanmanız gerekir.  
  
 İşlev adı veya işlev adıyla altında parametreleri anlamları ve işlevlerin dönüş değerleri belgelenen **üzerinde** etkileşimlidir. Örneğin, **CtlColor** belgelenen `OnCtlColor`. Birkaç yansıtılan ileti işleyicileri üst penceresinde benzer işleyicileri sayısından daha az sayıda parametre gerekir. Yalnızca aşağıdaki tabloda adlarla belgelerinde biçimsel parametresi adları ile eşleşir.  
  
|Eşleme girişi|İşlev prototipi|  
|---------------|------------------------|  
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **();**|  
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *sonuç* **);**|  
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(Ccmduı\***  `pCmdUI` **);**|  
|**ON_WM_CTLCOLOR_REFLECT)**|**afx_msg HBRUSH CtlColor (CDC\***  `pDC` **, UINT** `nCtlColor` **);**|  
|**ON_WM_DRAWITEM_REFLECT)**|**afx_msg void DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|  
|**ON_WM_MEASUREITEM_REFLECT)**|**afx_msg void MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|  
|**ON_WM_DELETEITEM_REFLECT)**|**afx_msg void DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|  
|**ON_WM_COMPAREITEM_REFLECT)**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|  
|**ON_WM_CHARTOITEM_REFLECT)**|**afx_msg int CharToItem (UINT** `nKey` **, UINT** `nIndex` **);**|  
|**ON_WM_VKEYTOITEM_REFLECT)**|**afx_msg int VKeyToItem (UINT** `nKey` **, UINT** `nIndex` **);**|  
|**ON_WM_HSCROLL_REFLECT)**|**afx_msg void HScroll (UINT** `nSBCode` **, UINT** `nPos` **);**|  
|**ON_WM_VSCROLL_REFLECT)**|**afx_msg void VScroll (UINT** `nSBCode` **, UINT** `nPos` **);**|  
|**ON_WM_PARENTNOTIFY_REFLECT)**|**afx_msg void ParentNotify (UINT** `message` **, LPARAM** `lParam` **);**|  
  
 **On_notıfy_reflect** ve **ON_CONTROL_REFLECT** makroları (örneğin, Denetim ve kendi üst) birden fazla nesne belirli bir ileti işlemeye izin Çeşitlemeler vardır.  
  
|Eşleme girişi|İşlev prototipi|  
|---------------|------------------------|  
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *sonuç* **);**|  
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **();**|  
  
## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>İşleme Reflected iletileri: Yeniden kullanılabilir bir denetim örneği  
 Bu basit örnek olarak adlandırılan yeniden kullanılabilir bir denetim oluşturur `CYellowEdit`. Sarı bir arka plan üzerinde siyah metin görüntüler denetimi normal düzenleme denetimi ile aynı çalışır. İzin üye işlevleri eklemek kolay `CYellowEdit` farklı renkler görüntülemek için denetimi.  
  
#### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Örnek denemek için yeniden kullanılabilir bir denetim oluşturur  
  
1.  Yeni bir iletişim kutusu var olan bir uygulama oluşturun. Daha fazla bilgi için bkz: [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) konu.  
  
     Yeniden kullanılabilir denetim geliştirmek üzere bir uygulama olmalıdır. Kullanmak için varolan bir uygulamaya sahip olmamaları durumunda AppWizard kullanarak iletişim tabanlı bir uygulama oluşturun.  
  
2.  Visual C++ yüklenen projenizle ClassWizard adlı yeni bir sınıf oluşturmak için kullanın. `CYellowEdit` göre `CEdit`.  
  
3.  Üç üye değişkenleri ekleyip, `CYellowEdit` sınıfı. İlk iki olacaktır **COLORREF** metin rengini ve arka plan rengini tutması için değişkenleri. Üçüncü olacak bir `CBrush` arka plan boyama için fırça tutacak nesne. `CBrush` Nesne sağlar, bir kez, yalnızca bundan sonra başvuran Fırça oluşturma ve fırça otomatik olarak ne zaman yok etmek için `CYellowEdit` denetim yok.  
  
4.  Üye değişkenleri Oluşturucusu gibi yazarak başlatın:  
  
 ```  
    CYellowEdit::CYellowEdit() 
 {  
    m_clrText = RGB(0,
    0,
    0);

    m_clrBkgnd = RGB(255,
    255,
    0);

    m_brBkgnd.CreateSolidBrush(m_clrBkgnd);

 }  
 ```  
  
5.  ClassWizard, kullanarak yansıtılan için bir işleyici ekleyin `WM_CTLCOLOR` için ileti, `CYellowEdit` sınıfı. İleti adı işleyebilir iletiler listesinde önünde eşittir işareti ileti yansıtılır olduğuna dikkat edin. Bu açıklanan [yansıtılan bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).  
  
     ClassWizard sizin için aşağıdaki ileti eşleme makrosu ve çatıyı işlevi ekler:  
  
 ```  
    ON_WM_CTLCOLOR_REFLECT() 
 *// Note: other code will be in between....  
 
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
 { *// TODO: Change any attributes of the DC here  
 *// TODO: Return a non-NULL brush if the *//   parent's handler should not be called  
    return NULL;  
 }  
 ```  
  
6.  İşlev gövdesi aşağıdaki kodla değiştirin. Kod metin rengi, metin arka plan rengi ve rest denetimin arka plan rengini belirtir.  
  
 ```  
    pDC->SetTextColor(m_clrText);
*// text  
    pDC->SetBkColor(m_clrBkgnd);
*// text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
 ```  
  
7.  İletişim kutusunda bir düzen denetimi oluşturma ve CTRL tuşunu basılı çalışırken düzenleme denetimi çift tıklayarak bir üye değişkeni ekleme. Üye değişkeni ekleme iletişim kutusunda, değişken adını tamamlayın ve ardından "CYellowEdit" için değişken türü kategori için "Denetim"'i seçin. İletişim kutusunda sekme sırasını ayarlamayı unutmayın. Ayrıca, üstbilgi dosyası için eklediğinizden emin olun `CYellowEdit` iletişim kutusunun üst bilgi dosyası denetiminde.  
  
8.  Derleme ve uygulamanızı çalıştırın. Düzenleme denetimi sarı bir arka plan sahip olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

