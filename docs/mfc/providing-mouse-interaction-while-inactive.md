---
description: 'Daha fazla bilgi edinin: etkin olmadığında fare etkileşimi sağlama'
title: Devre Dışı İken Fare Etkileşimi Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: bd3c069b052b58059de5f311e4ead795400d32fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248742"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Devre Dışı İken Fare Etkileşimi Sağlama

Denetiminiz hemen etkinleştirilmemişse, denetimin kendi penceresi olmasa bile WM_SETCURSOR ve WM_MOUSEMOVE iletileri işlemesini hala isteyebilirsiniz. Bu, `COleControl` `IPointerInactive` Varsayılan olarak devre dışı bırakılan arabirimin uygulamasını etkinleştirerek gerçekleştirilebilir. (Bu arabirimin açıklaması için bkz. *ACTIVEX SDK* .) Bunu etkinleştirmek için [Coelcontrol:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen Flags kümesine Pointerınactıve bayrağını ekleyin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

Bu bayrağı dahil etme kodu, **MFC ActiveX Denetim Sihirbazı** ile denetiminizi oluştururken [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında **etkin olmadığında fare işaretçisi bildirimleri** seçeneğini belirlerseniz otomatik olarak üretilir.

`IPointerInactive`Arabirim etkinleştirildiğinde kapsayıcı WM_SETCURSOR ve WM_MOUSEMOVE iletileri devreder. `COleControl`uygulamasının, `IPointerInactive` fare koordinatlarını uygun şekilde ayarladıktan sonra iletileri denetiminizin ileti haritalarıyla dağıtır. İleti eşlemesine karşılık gelen girdileri ekleyerek sıradan pencere iletileri gibi iletileri işleyebilirsiniz. Bu iletilere yönelik İşleyicileriniz içinde, ilk olarak değerinin **null** olmadığını kontrol etmeden *m_hWnd* üye değişkeni (veya onu kullanan herhangi bir üye işlevi) kullanmaktan kaçının.

Etkin olmayan bir denetimin bir OLE sürükle ve bırak işleminin hedefi olmasını de isteyebilirsiniz. Bu, denetimin penceresinin bir bırakma hedefi olarak kaydedileceği şekilde kullanıcının bir nesneyi sürüklediği anda denetimin etkinleştirilmesini gerektirir. Bir sürükleme sırasında etkinleştirmenin oluşmasına neden olmak için [Cotacontrol:: GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)' yi geçersiz kılın ve POINTERINACTIVE_ACTIVATEONDRAG bayrağını döndürün:

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

Arabirimin etkinleştirilmesi `IPointerInactive` genellikle denetimin, fare iletilerini her zaman işleyebilmesini istediğiniz anlamına gelir. Bu davranışı arabirimi desteklemeyen bir kapsayıcıda almak için `IPointerInactive` , denetimin her zaman görünür hale getirmeniz gerekir, bu da denetimin çeşitli bayrakları arasında OLEMISC_ACTIVATEWHENVISIBLE bayrağını içermesi gerektiği anlamına gelir. Ancak, bu bayrağın desteklenen bir kapsayıcıda etkili olmasını engellemek için `IPointerInactive` OLEMISC_IGNOREACTIVATEWHENVISIBLE bayrağını da belirtebilirsiniz:

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](../mfc/mfc-activex-controls-optimization.md)
