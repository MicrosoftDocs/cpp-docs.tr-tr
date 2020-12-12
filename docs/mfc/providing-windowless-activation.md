---
description: 'Daha fazla bilgi edinin: penceresiz etkinleştirme sağlama'
title: Penceresiz Etkinleştirme Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
ms.openlocfilehash: ea9b86c977926e57bd3593ec861498eb5d909f37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248638"
---
# <a name="providing-windowless-activation"></a>Penceresiz Etkinleştirme Sağlama

Pencere oluşturma kodu (diğer bir deyişle, çağırdığınızda gerçekleşen her şey `CreateWindow` ) yürütmek için maliyetli bir şeydir. Bir ekran penceresinin bakımını yapan bir denetimin pencere için iletileri yönetmesi vardır. Penceresiz denetimler bu nedenle Windows ile denetimlerden daha hızlıdır.

Penceresiz denetimlerin daha fazla avantajı, pencereli denetimlerin aksine, penceresiz denetimlerin saydam boyama ve dikdörtgen olmayan ekran bölgelerini desteklemeleridir. Saydam bir denetimin ortak bir örneği, saydam bir arka plana sahip bir metin denetimidir. Denetimler, metni boyar ancak arka planı değil, metnin altında olduğu şekilde görünür. Daha yeni formlar genellikle oklar ve yuvarlak düğmeleri gibi dikdörtgen olmayan denetimleri kullanır.

Genellikle, bir denetim kendi penceresine gerek kalmaz ve bunun yerine, kapsayıcının penceresiz nesneleri desteklemek üzere yazıldığı belirtilen kapsayıcının pencere hizmetlerini kullanabilir. Penceresiz denetimler eski kapsayıcılarla geriye dönük olarak uyumludur. Penceresiz denetimleri desteklemek için yazılmayan eski kapsayıcılarda, Penceresiz denetimleri etkin olduğunda bir pencere oluşturur.

Penceresiz denetimlerin kendi pencereleri olmadığından, kapsayıcı (bir pencerenin bulunduğu), başka türlü denetimin kendi penceresi tarafından sağlanabilecek Hizmetleri sağlamaktan sorumludur. Örneğin, denetiminizin klavye odağını sorgulaması, fareyi yakalaması veya bir cihaz bağlamı alması gerekiyorsa, bu işlemler kapsayıcı tarafından yönetilir. Kapsayıcı, penceresine gönderilen Kullanıcı giriş iletilerini, arabirimini kullanarak uygun penceresiz denetime yönlendirir `IOleInPlaceObjectWindowless` . (Bu arabirimin açıklaması için bkz. *ACTIVEX SDK* .) `COleControl` üye işlevleri bu Hizmetleri kapsayıcıdan çağırır.

Denetiminizin penceresiz etkinleştirme kullanmasını sağlamak için, [Coelcontrol:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen bayrak kümesine **windowlessacıı** bayrağını ekleyin. Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]

MFC ActiveX Denetim Sihirbazı 'nın [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında **penceresiz etkinleştirme** seçeneğini belirlerseniz, bu bayrağı dahil etme kodu otomatik olarak üretilir.

Penceresiz etkinleştirme etkinleştirildiğinde kapsayıcı, giriş iletilerini denetim arabirimine devredebilir `IOleInPlaceObjectWindowless` . `COleControl`Bu arabirimin uygulanması, fare koordinatlarını uygun şekilde ayarladıktan sonra iletileri denetiminizin ileti haritalarıyla dağıtır. İleti eşlemesine karşılık gelen girdileri ekleyerek sıradan pencere iletileri gibi iletileri işleyebilirsiniz. Bu iletilere yönelik İşleyicileriniz içinde, ilk olarak değerinin **null** olmadığını kontrol etmeden *m_hWnd* üye değişkeni (veya onu kullanan herhangi bir üye işlevi) kullanmaktan kaçının.

`COleControl` kapsayıcıdan uygun şekilde, fare yakalama, klavye odağı, kaydırma ve diğer pencere hizmetlerini çağıran üye işlevleri sağlar; örneğin:

- [GetFocus](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)

- [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)

- [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)

- [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)

- [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)

- [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)

Penceresiz denetimlerde, `COleControl` ilgili `CWnd` üye işlevleri veya ilgili Win32 API işlevleri yerine her zaman üye işlevlerini kullanmanız gerekir.

Penceresiz bir denetimin bir OLE sürükle ve bırak işleminin hedefi olmasını isteyebilirsiniz. Normalde, bu, denetimin penceresinin bırakma hedefi olarak kaydedilmesini gerektirir. Denetimin kendi penceresi olmadığından kapsayıcı, bir bırakma hedefi olarak kendi penceresini kullanır. Denetim, `IDropTarget` kapsayıcının çağrıları uygun zamanda temsil eden arabirimin bir uygulamasını sağlar. Bu arabirimi kapsayıcıya göstermek için [Cotacontrol:: GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget)öğesini geçersiz kılın. Örneğin:

[!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](../mfc/mfc-activex-controls-optimization.md)
