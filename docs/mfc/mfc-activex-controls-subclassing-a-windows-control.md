---
title: 'MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma'
ms.date: 09/12/2018
f1_keywords:
- precreatewindow
- IsSubclassed
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
ms.openlocfilehash: ccebbad22be92b84fa2fd84434f788484d332cce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375993"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma

Bu makalede, activex denetimi oluşturmak için ortak bir Windows denetimi alt sınıflandırma işlemi açıklanmaktadır. Varolan bir Windows denetimini alt sınıflandırmak, ActiveX denetimini geliştirmenin hızlı bir yoludur. Yeni denetim, fare tıklamalarını boyama ve yanıt verme gibi alt sınıflanmış Windows denetiminin yeteneklerine sahip olacaktır. MFC ActiveX, örnek [BUTTON](../overview/visual-cpp-samples.md) denetimlerini bir Windows denetiminin alt sınıflanmasına bir örnektir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Windows denetimini alt sınıfa almak için aşağıdaki görevleri tamamlayın:

- [COleControl'un IsSubclassedControl ve PreCreateWindow üye işlevlerini geçersiz kılın](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw üye işlevini değiştirme](#_core_modifying_the_ondraw_member_function)

- [Kontrole yansıyan herhangi bir ActiveX kontrol iletisini (OCM) işleme](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > Bu çalışmanın çoğu, **Denetim Ayarları** sayfasındaki **Üst Pencere Sınıfı** açılır listesini kullanarak alt sınıflanacak denetimi seçerseniz ActiveX Denetim Sihirbazı tarafından yapılır.

## <a name="overriding-issubclassedcontrol-and-precreatewindow"></a><a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>IsSubclassedControl ve PreCreateWindow Geçersiz Kılma

Geçersiz kılmak `PreCreateWindow` `IsSubclassedControl`ve denetim sınıfı bildiriminin **korumalı** bölümüne aşağıdaki kod satırlarını eklemek için:

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

Denetim uygulama dosyasında (. CPP), iki geçersiz kılınan işlevleri uygulamak için aşağıdaki kod satırlarını ekleyin:

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

Bu örnekte, Windows düğmesi denetiminin `PreCreateWindow`. Ancak, herhangi bir standart Windows denetimleri alt sınıflanabilir. Standart Windows denetimleri hakkında daha fazla bilgi için [bkz.](../mfc/controls-mfc.md)

Bir Windows denetimini alt sınıflandırırken, denetim penceresi oluştururken kullanılacak belirli pencere stilini (WS_) veya genişletilmiş pencere stili (WS_EX_) bayraklarını belirtmek isteyebilirsiniz. Bu parametreler için üye işlevdeki değerleri, `cs.dwExStyle` yapı `cs.style` alanlarını ve yapı alanlarını değiştirerek ayarlayabilirsiniz. `PreCreateWindow` Bu alanlarda yapılan değişiklikler, sınıfa `COleControl`göre ayarlanan varsayılan bayrakları korumak için bir **OR** işlemi kullanılarak yapılmalıdır. Örneğin, denetim BUTTON denetimini alt sınıflıyorsa ve denetimin bir onay kutusu olarak görünmesini istiyorsanız, `CSampleCtrl::PreCreateWindow`iade deyiminden önce aşağıdaki kod satırını uygulamaya ekleyin:

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

Bu işlem, sınıfın `COleControl` varsayılan stil bayrağını (WS_CHILD) bozulmadan bırakırken BS_CHECKBOX stili bayrağını ekler.

## <a name="modifying-the-ondraw-member-function"></a><a name="_core_modifying_the_ondraw_member_function"></a>OnDraw Üye Işlevini Değiştirme

Alt sınıf denetiminizin ilgili Windows denetimiyle aynı görünümü korumasını istiyorsanız, denetimin `OnDraw` üye işlevi `DoSuperclassPaint` aşağıdaki örnekte olduğu gibi yalnızca üye işlevine bir çağrı içermelidir:

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

Tarafından `DoSuperclassPaint` uygulanan üye `COleControl`işlev, sınırlayan dikdörtgen içinde, belirtilen aygıt bağlamında denetim çizmek için Windows denetiminin pencere yordamını kullanır. Bu, etkin olmasa bile denetimi görünür kılar.

> [!NOTE]
> Üye `DoSuperclassPaint` işlev, yalnızca aygıt bağlamının WM_PAINT bir iletinin *wParam'ı* olarak geçirilmesine izin veren denetim türleri ile çalışır. Buna SCROLLBAR ve BUTTON gibi standart Windows denetimlerinden bazıları ve tüm ortak denetimler dahildir. Bu davranışı desteklemeyen denetimler için, etkin olmayan bir denetimi düzgün bir şekilde görüntülemek için kendi kodunuzu sağlamanız gerekir.

## <a name="handling-reflected-window-messages"></a><a name="_core_handling_reflected_window_messages"></a>Yansıyan Pencere İletilerini Işleme

Windows denetimleri genellikle üst pencerelerine belirli pencere iletileri gönderir. bu iletilerin bazıları(WM_COMMAND gibi, kullanıcı tarafından bir eylemin bildirimini sağlar. WM_CTLCOLOR gibi diğerleri, üst pencereden bilgi almak için kullanılır. ActiveX denetimi genellikle ana pencereyle başka yollarla iletişim kurar. Bildirimler, olay bildirimleri gönderilerek (olay bildirimleri gönderilerek) iletilir ve kontrol konteyneri ile ilgili bilgiler konteynerin ortam özelliklerine erişilerek elde edilir. Bu iletişim teknikleri mevcut olduğundan, ActiveX denetim kapları denetim tarafından gönderilen herhangi bir pencere iletileri işlemek için beklenmez.

Kapsayıcının alt sınıflı bir Windows denetimi tarafından gönderilen pencere `COleControl` iletilerini almasını önlemek için, denetimin üst öğesi olarak hizmet vermek için fazladan bir pencere oluşturur. "Yansıtıcı" adı verilen bu ek pencere, yalnızca Windows denetimini alt sınıflayan ve denetim penceresiyle aynı boyut ve konuma sahip bir ActiveX denetimi için oluşturulur. Reflektör penceresi belirli pencere iletilerini yakalar ve bunları denetime geri gönderir. Denetim, pencere yordamında, daha sonra activex denetimi için uygun eylemleri gerçekleştirerek (örneğin, bir olayı ateşleyerek) bu yansıyan iletileri işleyebilir. Ele geçirilen windows iletilerinin ve bunların karşılık gelen yansıyan iletilerinin listesi için [Yansıyan Pencere İletisi Kimliklerini](../mfc/reflected-window-message-ids.md) görün.

ActiveX denetim kapsayıcısı, reflektör penceresi oluşturma gereksinimini `COleControl` ortadan kaldırarak ve alt sınıflanmış bir Windows denetimi için çalışma süresini azaltarak ileti yansımasının kendisini gerçekleştirmek üzere tasarlanabilir. `COleControl`**TRUE**değeri olan bir MessageReflect ortam özelliğini denetleyerek kapsayıcının bu özelliği destekleyip desteklemediğini algılar.

Yansıyan bir pencere iletisini işlemek için denetim iletisi eşlemi'ne bir giriş ekleyin ve işleyici işlevi uygulayın. Yansıyan iletiler Windows tarafından tanımlanan standart ileti kümesinin bir parçası olmadığından, Sınıf Görünümü bu tür ileti işleyicileri eklemeyi desteklemez. Ancak, bir işleyiciyi el ile eklemek zor değildir.

Yansıyan bir pencere iletisi için ileti işleyicisi eklemek için el ile aşağıdakileri yapın:

- Kontrol sınıfında. H dosyası, bir işleyici işlevi bildirin. İşlev, sırasıyla **WPARAM** ve **LPARAM**tiplerine sahip bir **LRESULT** ve iki parametre nin dönüş türüne sahip olmalıdır. Örneğin:

   [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- Kontrol sınıfında. CPP dosyası, ileti eşlemi ON_MESSAGE bir giriş ekleyin. Bu girişin parametreleri ileti tanımlayıcısı ve işleyici işlevinin adı olmalıdır. Örneğin:

   [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- Ayrıca içinde . CPP dosyası, `OnOcmCommand` yansıyan iletiyi işlemek için üye işlevini uygulayın. *wParam* ve *lParam* parametreleri orijinal pencere iletisi ile aynıdır.

Yansıyan iletilerin nasıl işlendiğine bir örnek olarak, MFC ActiveX denetimleri örnek [DÜĞMESINe](../overview/visual-cpp-samples.md)bakın. BN_CLICKED bildirim `OnOcmCommand` kodunu algılayan ve bir olayı ateşleyerek (göndererek) `Click` yanıt veren bir işleyici gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
