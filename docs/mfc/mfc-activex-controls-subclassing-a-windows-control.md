---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: Altsınıflama a Windows Control'
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
ms.openlocfilehash: f3ea0e1af9860ca4585fe31817c689b75241d0f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164113"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma

Bu makalede, bir ActiveX denetimi oluşturmak için ortak bir Windows denetimi altsınıflama için işlem açıklanır. Altsınıflama var olan bir Windows denetimi, ActiveX denetimi geliştirmenin hızlı bir yoludur. Yeni denetim, boyama ve fare tıklamasına yanıt verme gibi alt sınıflı Windows denetiminin yeteneklerine sahip olacaktır. MFC ActiveX denetimleri örnek [düğmesi](../overview/visual-cpp-samples.md) , bir Windows denetimi altsınıflama örneğidir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bir Windows denetimini alt sınıflara ayırmak için aşağıdaki görevleri doldurun:

- [Coelcontrol 'ın ıbıkı](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw üye işlevini değiştirme](#_core_modifying_the_ondraw_member_function)

- [Denetime yansıtılan tüm ActiveX denetim iletilerini (OCM) işleme](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > **Denetim ayarları** sayfasında **ana pencere sınıfı seç** açılan listesini kullanarak alt sınıflandırılacak denetim ' i seçerseniz, bu çalışmanın çoğu sizin için ActiveX Denetim Sihirbazı tarafından yapılır.

## <a name="overriding-issubclassedcontrol-and-precreatewindow"></a><a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> Ibıtsedcontrol ve ön Reatewindow geçersiz kılınıyor

`PreCreateWindow`Ve ' yi geçersiz kılmak için `IsSubclassedControl` , **`protected`** Denetim sınıfı bildiriminin bölümüne aşağıdaki kod satırlarını ekleyin:

[!code-cpp[NVC_MFC_AxSub#1](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

Denetim uygulama dosyasında (. CPP), geçersiz kılınan iki işlevi uygulamak için aşağıdaki kod satırlarını ekleyin:

[!code-cpp[NVC_MFC_AxSub#2](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

Bu örnekte, Windows düğme denetiminin ' de belirtildiğine dikkat edin `PreCreateWindow` . Ancak, tüm standart Windows denetimleri alt sınıflı olabilir. Standart Windows denetimleri hakkında daha fazla bilgi için bkz. [denetimler](controls-mfc.md).

Bir Windows denetimini altsınıflama, denetimin penceresini oluştururken kullanılacak belirli pencere stilini (WS_) veya genişletilmiş pencere stili (WS_EX_) bayraklarını belirtmek isteyebilirsiniz. `PreCreateWindow` `cs.style` Ve yapı alanlarını değiştirerek üye işlevindeki bu parametrelerin değerlerini ayarlayabilirsiniz `cs.dwExStyle` . Sınıf tarafından ayarlanan varsayılan bayrakları korumak için bu alanlarda yapılan değişiklikler **veya** işlem kullanılarak yapılmalıdır `COleControl` . Örneğin, denetim düğme denetimini altsınıflama ve denetimin onay kutusu olarak görünmesini istiyorsanız, `CSampleCtrl::PreCreateWindow` Return ifadesinden önce, uygulamasının uygulamasına aşağıdaki kod satırını ekleyin:

[!code-cpp[NVC_MFC_AxSub#3](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

Bu işlem, sınıfın varsayılan stil bayrağını (WS_CHILD) koruyarak BS_CHECKBOX stil bayrağını ekler `COleControl` .

## <a name="modifying-the-ondraw-member-function"></a><a name="_core_modifying_the_ondraw_member_function"></a> OnDraw üye Işlevini değiştirme

Alt sınıflı denetiminizin ilgili Windows denetimiyle aynı görünümü tutmasını istiyorsanız, `OnDraw` denetimin üye işlevi, `DoSuperclassPaint` Aşağıdaki örnekte olduğu gibi yalnızca üye işlevine bir çağrı içermelidir:

[!code-cpp[NVC_MFC_AxSub#4](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

`DoSuperclassPaint`Tarafından uygulanan üye işlevi, `COleControl` denetimi belirtilen cihaz bağlamında (sınırlayıcı dikdörtgen içinde) çizmek için Windows denetiminin pencere yordamını kullanır. Bu, denetim etkin olmadığında bile görünür hale gelir.

> [!NOTE]
> `DoSuperclassPaint`Üye işlevi yalnızca bir cihaz bağlamının WM_PAINT bir Iletinin *wParam* olarak geçirilmesini sağlayan denetim türleriyle çalışır. Bu, KAYDıRMA çubuğu ve düğme gibi bazı standart Windows denetimlerini ve tüm ortak denetimleri içerir. Bu davranışı desteklemeyen denetimler için, etkin olmayan bir denetimi doğru şekilde göstermek üzere kendi kodunuzu sağlamanız gerekir.

## <a name="handling-reflected-window-messages"></a><a name="_core_handling_reflected_window_messages"></a> Yansıtılan pencere Iletilerini işleme

Windows denetimleri, genellikle belirli pencere iletilerini üst penceresine gönderir. WM_COMMAND gibi bu iletilerden bazıları Kullanıcı tarafından bir eyleme ilişkin bildirim sağlar. WM_CTLCOLOR gibi diğerleri, üst pencereden bilgi almak için kullanılır. Bir ActiveX denetimi genellikle üst pencereyle diğer yollarla iletişim kurar. Bildirimler olayları (olay bildirimleri gönderiliyor) tetikleyerek ve Denetim kapsayıcısı hakkındaki bilgiler kapsayıcının çevresel özelliklerine erişerek elde edilir. Bu iletişim teknikleri mevcut olduğundan, ActiveX denetim kapsayıcılarının denetim tarafından gönderilen herhangi bir pencere iletisini işlemesi beklenmez.

Kapsayıcının, alt sınıf Windows denetimi tarafından gönderilen pencere iletilerini almasını engellemek için `COleControl` denetimin üst öğesi olarak kullanılacak ek bir pencere oluşturur. "Yansıtıcısı" adlı bu ek pencere, yalnızca bir Windows denetimini alt sınıflara uygulayan ve denetim penceresiyle aynı boyuta ve konuma sahip olan bir ActiveX denetimi için oluşturulur. Yansıtıcısı penceresi bazı pencere iletilerini karşılar ve bunları denetime geri gönderir. Bu denetim, kendi pencere yordamında, ActiveX denetimine uygun eylemleri (örneğin, bir olay tetikleyerek) gerçekleştirerek bu yansıtılan iletileri işleyebilir. Kesilen Windows iletileri ve bunlara ait yansıtılan iletiler listesi için bkz. [yansıtılan pencere Iletisi kimlikleri](reflected-window-message-ids.md) .

Bir ActiveX Denetim kapsayıcısı ileti yansıtma kendisini gerçekleştirecek şekilde tasarlanmış olabilir, bu da `COleControl` yansıtıcı pencere oluşturma ve alt sınıflı bir Windows denetimi için çalışma zamanı ek yükünü azaltma ihtiyacını ortadan kaldırır. `COleControl`**doğru** değeri olan bir Messagerefbir ortam özelliği olup olmadığını, kapsayıcının bu yeteneği destekleyip desteklemediğini algılar.

Yansıtılan bir pencere iletisini işlemek için denetim iletisi eşlemesine bir giriş ekleyin ve bir işleyici işlevi uygulayın. Yansıtılan iletiler Windows tarafından tanımlanan standart ileti kümesinin bir parçası olmadığından, Sınıf Görünümü bu tür ileti işleyicilerini eklemeyi desteklemez. Ancak, işleyicinin el ile eklenmesi zor değildir.

Yansıtılan bir pencere iletisine yönelik bir ileti işleyicisi eklemek için aşağıdakileri el ile yapın:

- Denetim sınıfında. H dosyası, bir işleyici işlevi bildirin. İşlev, sırasıyla **wParam** ve **lParam** türünde olan **LRESULT** ve iki parametre dönüş türüne sahip olmalıdır. Örneğin:

   [!code-cpp[NVC_MFC_AxSub#5](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- Denetim sınıfında. CPP dosyası, ileti eşlemesine bir ON_MESSAGE girişi ekleyin. Bu girdinin parametreleri ileti tanımlayıcısı ve işleyici işlevinin adı olmalıdır. Örneğin:

   [!code-cpp[NVC_MFC_AxSub#7](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- Ayrıca,. CPP dosyası, `OnOcmCommand` yansıtılan iletiyi işlemek için üye işlevini uygulayın. *WParam* ve *lParam* parametreleri özgün pencere iletisiyle aynıdır.

Yansıtılan iletilerin nasıl işlendiği hakkında bir örnek için MFC ActiveX denetimleri örnek [düğmesine](../overview/visual-cpp-samples.md)başvurun. `OnOcmCommand`BN_CLICKED bildirim kodunu algılayan ve bir olayı tetikleyerek (göndererek) yanıt veren bir işleyiciyi gösterir `Click` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
