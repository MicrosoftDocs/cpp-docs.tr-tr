---
title: Devre Dışı İken Fare Etkileşimi Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: d37deeec06551ae8bf340c99a9759327ce2ec2b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297131"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Devre Dışı İken Fare Etkileşimi Sağlama

Denetiminiz hemen etkinleştirilmemesi halinde denetimi penceresi kendi sahip olsa da işlem WM_SETCURSOR ve WM_MOUSEMOVE iletileri isteyebilirsiniz. Bu etkinleştirerek gerçekleştirilebilir `COleControl`'s uygulaması `IPointerInactive` arabirimi, varsayılan olarak devre dışıdır. (Bkz *ActiveX SDK* bu arabirim açıklaması.) Bunu etkinleştirmek için bayrakları tarafından döndürülen dizi pointerInactive bayrağını ekleyin. [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

Seçerseniz bu bayrak eklenecek kodu otomatik olarak oluşturulan **fare işaretçisi bildirimleri, etkin olmayan** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında denetiminiz ileoluştururken**MFC ActiveX Denetim Sihirbazı**.

Zaman `IPointerInactive` arabirimi etkin olduğunda, kapsayıcı WM_SETCURSOR ve WM_MOUSEMOVE iletileri buna atar. `COleControl`ın uygulaması `IPointerInactive` fare ayarlama uygun şekilde düzenler sonra denetiminizin ileti eşlemesi aracılığıyla iletileri gönderir. İleti eşlemesi için karşılık gelen girişler ekleyerek iletileri sıradan pencere iletileri gibi işleyebilir. Bu iletiler, işleyicilerindeki kullanmaktan kaçının *m_hWnd* üye değişkeni (veya onu kullanan herhangi bir üye işlevini) değerini değil olmadığını denetlemeden **NULL**.

OLE sürükle ve bırak işleminin hedefi için etkin olmayan bir denetimi de isteyebilirsiniz. Bu, böylece bir bırakma hedefi denetim pencere kaydedilebilir kullanıcı nesnenin üzerine sürüklediğinde anda denetimi etkinleştirme gerektirir. Bir sürükleme sırasında etkinleştirme neden olmak için geçersiz kılma [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)ve POINTERINACTIVE_ACTIVATEONDRAG bayrağı döndürür:

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

Etkinleştirme `IPointerInactive` arabirimi genellikle anlamına gelir her zaman fare iletileri işleyebilme yeteneği olmasını istiyor. Desteklemeyen bir kapsayıcıda bu davranışı elde etmek üzere `IPointerInactive` arabirimi denetiminiz görünür olduğunda, her zaman etkin olması gerekir denetimi başka bir deyişle, çeşitli bayraklarının arasında OLEMISC_ACTIVATEWHENVISIBLE bayrak içermelidir. Ancak, bu bayrağı önlemek için etkili bir kapsayıcıda alma destekliyor mu `IPointerInactive`, OLEMISC_IGNOREACTIVATEWHENVISIBLE bayrağı da belirtebilirsiniz:

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md)
