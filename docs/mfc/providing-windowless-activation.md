---
title: Penceresiz etkinleştirme sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e8fc079921b3f2eddd117f93ee9d2f6cad60925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441234"
---
# <a name="providing-windowless-activation"></a>Penceresiz Etkinleştirme Sağlama

Pencere oluşturma kod (diğer bir deyişle, gerçekleşen her şeyi çağırdığınızda `CreateWindow`) yürütmek maliyetlidir. Tutan bir denetimi bir ekrandaki penceresi bir pencere için iletileri yönetmesi gerekir. Penceresiz denetimleri, bu nedenle windows denetimleriyle kıyasla daha hızlı.

Penceresiz denetimleri başka bir avantajı pencereli denetimleri penceresiz denetimleri saydam boyama ve dikdörtgen olmayan ekran bölgeleri, desteklemesidir. Yaygın olarak karşılaşılan örneklerden saydam bir denetimin, saydam arka plana sahip bir metin denetimidir. Denetimleri boyar metin ancak arka plan değil, ne olursa olsun altındaki metin aracılığıyla gösterecek şekilde. Yeni form genellikle ok gibi dikdörtgen olmayan denetimleri kullanın ve düğmeler yuvarlak olun.

Genellikle, bir denetim bir pencere kendi gerekmez ve kapsayıcı penceresiz nesneleri desteklemek üzere yazılmış belirtilen bunun yerine, kendi kapsayıcı penceresi hizmetlerini kullanabilirsiniz. Penceresiz denetimleri, eski kapsayıcılar ile geriye dönük olarak uyumludur. Penceresiz denetimleri desteklemek üzere yazılmış değil, eski kapsayıcılarda bir pencere etkin olduğunda penceresiz denetimler oluşturun.

Penceresiz denetimleri kendi windows olmadığı için Aksi takdirde denetimin kendi pencere tarafından sağlanan hizmetleri sağlamak için (bir pencere sahip) kapsayıcı sorumludur. Örneğin, klavye odağı sorgu, fare yakalama veya bir cihaz bağlamı elde etmek denetim gerekiyorsa bu işlemler kapsayıcı tarafından yönetilir. Kullanıcı giriş iletileri kendi penceresini uygun penceresiz denetime gönderilen kapsayıcı yönlendiren kullanarak `IOleInPlaceObjectWindowless` arabirimi. (Bkz *ActiveX SDK* bu arabirim açıklaması.) `COleControl` üye işlevleri çağırma kapsayıcısından bu hizmetler.

Penceresiz etkinleştirmesi kullanın, bir denetim yapmak için dahil **windowlessActivate** bayrağı tarafından döndürülen bayrakları kümesini [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]

Seçerseniz bu bayrak eklenecek kodu otomatik olarak oluşturulan **penceresiz etkinleştirme** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX Denetim Sihirbazı'nın sayfa.

Penceresiz etkinleştirme etkinleştirildiğinde, kapsayıcı denetimin giriş iletilerini temsil edecek `IOleInPlaceObjectWindowless` arabirimi. `COleControl`kullanıcının bu arabirimin fare ayarlama uygun şekilde düzenler sonra denetiminizin ileti eşlemesi aracılığıyla iletileri gönderir. İleti eşlemesi için karşılık gelen girişler ekleyerek iletileri sıradan pencere iletileri gibi işleyebilir. Bu iletiler, işleyicilerindeki kullanmaktan kaçının *m_hWnd* üye değişkeni (veya onu kullanan herhangi bir üye işlevini) değerini değil olmadığını denetlemeden **NULL**.

`COleControl` Fare yakalama, klavye odağı, kaydırma ve diğer penceresi Hizmetleri dahil olmak üzere uygun şekilde kapsayıcısından çağıran işlevleri sağlar:

- [Tıklatma](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)

- [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)

- [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)

- [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)

- [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)

- [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)

Her zaman kullanmalısınız penceresiz denetimlerinde `COleControl` karşılık gelen yerine üye işlevleri `CWnd` üye işlevleri veya kendi ilgili Win32 API işlevleri.

OLE sürükle ve bırak işleminin hedefi penceresiz denetime isteyebilirsiniz. Normalde, bu denetimin penceresindeki bir bırakma hedefi kaydedilmesi gerekir. Denetimi penceresi kendi olduğundan, kapsayıcı kendi penceresinde bir bırakma hedefi kullanır. Denetim bir uygulamasını sağlar `IDropTarget` istediğiniz kapsayıcıyı temsil edebilir çağrıları uygun zamanda arabirimi. Bu arabirim kapsayıcıya kullanıma sunmak için geçersiz kılma [COleControl::GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

