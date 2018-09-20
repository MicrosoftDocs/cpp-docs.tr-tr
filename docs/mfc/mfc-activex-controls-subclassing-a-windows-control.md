---
title: 'MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94b989594316f2eac3e65fad2cb5bf419e7ee2eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407554"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma

Bu makalede, bir ActiveX denetimi oluşturmak için ortak bir Windows denetimini alt sınıf yapma işlemi açıklanır. Mevcut bir Windows sınıflara denetim ActiveX denetimini geliştirmek için bir hızlı yoldur. Yeni Denetim boyama ve fare tıklamalarına yanıt verme gibi alt sınıflanan Windows denetimin yeteneklerini sahip olur. MFC ActiveX denetimleri örnek [düğmesi](../visual-cpp-samples.md) bir Windows denetimini alt sınıf yapma, bir örnek verilmiştir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Bir Windows denetimini alt sınıf için aşağıdaki görevleri tamamlayın:

- [COleControl Issubclassedcontrol ve PreCreateWindow üye işlevleri geçersiz kılma](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw üye işlevini Değiştir](#_core_modifying_the_ondraw_member_function)

- [Denetime yansıtılan tüm ActiveX denetim iletileri (OCM) işleme](#_core_handling_reflected_window_messages)

    > [!NOTE]
    >  Kullanarak sınıflandırılacak denetimi seçtiğinizde bu iş çoğunu sizin için ActiveX Denetim Sihirbazı tarafından yapılır **üst pencere sınıfını seçin** aşağı açılan listede **denetim ayarları** sayfası.

Bir denetimini alt sınıf yapma hakkında bilgi bankası makalesi Q243454 daha fazla bilgi için bkz.

##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> Issubclassedcontrol ve PreCreateWindow geçersiz kılma

Geçersiz kılınacak `PreCreateWindow` ve `IsSubclassedControl`, kod aşağıdaki satırları ekleyin **korumalı** denetim sınıf bildiriminin bölümünü:

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

Denetim uygulama dosyasında (. CPP), kod iki geçersiz kılınan işlevler uygulamak için aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

Bu örnekte, Windows Denetim düğmesi bildirimi belirtilen `PreCreateWindow`. Ancak, standart Windows denetimleri sınıflandırma. Standart Windows denetimleri hakkında daha fazla bilgi için bkz. [denetimleri](../mfc/controls-mfc.md).

Bir Windows denetimini alt sınıf yapma, belirli pencere stili (WS_) veya denetimin penceresi oluşturulurken kullanılacak genişletilmiş pencere stili (WS_EX_) bayrakları belirtmek isteyebilirsiniz. Bu parametreleri için değerler belirleyebileceğiniz `PreCreateWindow` değiştirerek üye işlevi `cs.style` ve `cs.dwExStyle` alanları yapılandırın. Değişiklikler bu alanlara kullanarak yapılacak bir **veya** sınıfı tarafından ayarlanmış varsayılan bayrakları korumak için işlem, `COleControl`. Örneğin, DÜĞME denetimini denetimini alt sınıf yapma ve bir onay kutusu olarak görünmesini istiyorsanız uygulamasına aşağıdaki kod satırını ekleyin `CSampleCtrl::PreCreateWindow`, dönüş deyiminden önce:

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

Bu işlem sınıfının varsayılan stili bayrağı (WS_CHILD) bırakarak BS_CHECKBOX stili bayrak ekler `COleControl` sağlam.

##  <a name="_core_modifying_the_ondraw_member_function"></a> OnDraw üye işlevi değiştirme

Karşılık gelen Windows Denetim aynı görünüme tutmak, sınıflandırılmış denetim istiyorsanız `OnDraw` denetimi için üye işlevi, yalnızca bir çağrı içermelidir `DoSuperclassPaint` aşağıdaki örnekteki gibi bir üye işlevi:

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

`DoSuperclassPaint` Üye işlevi, tarafından uygulanan `COleControl`, denetimin sınırlayıcı dikdörtgeni içinde belirtilen cihaz bağlamında çizmek için Windows Denetim pencere yordamını kullanır. Bile etkin olmadığı zaman denetimin görünür yapar.

> [!NOTE]
>  `DoSuperclassPaint` Üye işlevi, bir cihaz bağlamı olarak geçirilmesini sağlayan denetim türleri ile çalışır *wParam* WM_PAINT ileti. Bu, bazı kaydırma çubuğu ve DÜĞME gibi standart Windows denetimleri ve tüm ortak denetimleri içerir. Bu davranış desteklemeyen denetimler için etkin olmayan bir denetim düzgün görüntülenmesi için kendi kodunuzu sağlamanız gerekir.

##  <a name="_core_handling_reflected_window_messages"></a> Yansımış pencere iletilerini işleme

Windows denetimleri, genellikle belirli bir pencere iletileri kendi üst penceresine Gönder. WM_COMMAND gibi bu iletileri bazıları bildirim kullanıcı tarafından bir eylem sağlar. WM_CTLCOLOR gibi diğer üst penceresinden bilgi almak için kullanılır. ActiveX denetimi genellikle diğer yöntemlerle üst pencere ile iletişim kurar. Bildirimler (olay bildirimleri gönderme) olayları tetikleme tarafından iletildiği ve denetim kapsayıcısı hakkında bilgi kapsayıcının ortam özelliklerine erişme tarafından alınır. Bu iletişim teknikleri olmadığı için denetim tarafından gönderilen tüm pencere iletilerini işlemek için ActiveX denetim kapsayıcıları beklenmez.

Kapsayıcı sınıflandırılmış bir Windows Denetim tarafından gönderilen pencere iletilerini almasını önlemek için `COleControl` denetimin üst öğe olarak hizmet vermek için fazladan bir pencere oluşturur. Bir "reflector," olarak adlandırılan bu ek penceresinde, alt sınıfların bir Windows denetleyebilir ve aynı boyut ve konum denetim pencere sahip yalnızca bir ActiveX denetimi için oluşturulur. Reflector penceresi belirli pencere iletilerini yakalar ve bunları denetime geri gönderir. Denetimi alt pencere yordamını ardından (örneğin, bir olayı tetiklenmekte) bir ActiveX denetimi için uygun eylemleri gerçekleştirerek bu yansımış iletileri işleyebilir. Bkz: [yansımış pencere iletisi kimlikleri](../mfc/reflected-window-message-ids.md) yansımış iletiler ve bunlara karşılık gelen iletileri ilerlemesinden windows listesi için.

Bir ActiveX denetimi kapsayıcısı ihtiyacını ortadan ileti yansıması kendisi gerçekleştirmek için tasarlanmış olması `COleControl` reflector penceresi ve çalışma zamanı sınıflandırılmış bir Windows Denetim için ek yükü azaltarak oluşturmak için. `COleControl` kapsayıcı MessageReflect ortam özellik değerini denetleyerek bu özellik destekleyip desteklemediğini algılar **TRUE**.

Yansımış pencere iletisini işlemek için Denetim İleti eşlemesi için bir giriş ekleyin ve bir işleyici işlevi uygulayın. Yansımış iletileri standart Windows tarafından tanımlanan ileti kümesini parçası olmadığından, sınıf görünümü gibi bir ileti işleyicileri ekleme desteklemez. Ancak, el ile bir işleyici eklemek zor değildir.

Eklenecek ileti işleyicisi yansımış pencere iletisi için el ile aşağıdakileri yapın:

- Denetim sınıfı. H dosyasına bir işleyici işlevi bildirin. İşlev dönüş türü olmalıdır **LRESULT** ve türleriyle iki parametre **WPARAM** ve **LPARAM**sırasıyla. Örneğin:

     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- Denetim sınıfı. CPP için ileti eşlemesi ON_MESSAGE girişi ekleyin. Bu girdi parametrelerinin İleti tanımlayıcısı ve işleyici işlevinin adı olmalıdır. Örneğin:

     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- Ayrıca. CPP dosyasına uygulamak `OnOcmCommand` yansıtılan iletiyi işlemek için üye işlevi. *WParam* ve *lParam* parametreleri özgün pencere iletisi aynı olur.

MFC ActiveX denetimleri örneğe ilişkin bir örnek iletileri işlenme yansıtılan için başvurmak [düğmesi](../visual-cpp-samples.md). Bunu gösterir bir `OnOcmCommand` BN_CLICKED bildirim kod algılayan ve tetikleme (gönderen) ile yanıtlar işleyicisi bir `Click` olay.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

