---
title: 'MFC ActiveX Denetimleri: İyileştirme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
ms.openlocfilehash: cc4d210abe0bca5ba8d3a442796173111f45f6e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588571"
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX Denetimleri: İyileştirme

Bu makalede, ActiveX denetimleri daha iyi performans için en iyi duruma getirmek için kullanabileceğiniz teknikleri açıklar.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Konular [kapatma kapalı görünürken etkinleştir seçeneğini](../mfc/turning-off-the-activate-when-visible-option.md) ve [sağlama fare etkileşimi sırada etkin olmayan](../mfc/providing-mouse-interaction-while-inactive.md) etkinleştirilinceye kadar bir pencere oluşturma denetimleri tartışın. Konu [penceresiz etkinleştirme sağlama](../mfc/providing-windowless-activation.md) bile aktifleştirilmiş hiçbir zaman bir pencere oluşturma denetimleri açıklar.

Windows OLE nesneleri için iki ana dezavantajları vardır: Bunlar nesneleri saydam veya etkin olduğunda dikdörtgen olmayan engellemek ve büyük bir ek yük örnek oluşturma ve görüntüleme denetimleri ekleyin. Genellikle, bir pencere oluşturma denetimin oluşturulma zamanı yüzde 60'ını alır. Tek bir paylaşılan pencere (genellikle kapsayıcının) ve bazı dispatching kod ile denetim aynı penceresi Hizmetleri, genellikle bir performans kaybı olmadan alır. Bir pencere nesnesi için çoğunlukla gereksiz yük ise.

Denetiminiz belirli kapsayıcılarda kullanıldığında bazı iyileştirmeler mutlaka performansını değil. Örneğin, bu özelliği uygulamak eski kapsayıcılarında bir yararı sağlamaz şekilde 1996 önce yayımlanan kapsayıcıları penceresiz etkinleştirme desteklememektedir. Ancak, neredeyse tüm kapsayıcı Kalıcılık, destekler, böylece denetiminizin Kalıcılık kodu en iyi duruma getirme büyük olasılıkla tüm kapsayıcılarda performansını artırır. Denetim, özellikle kapsayıcı belirli bir tür ile kullanılacak amaçlanıyorsa, araştırmak, kapsayıcı tarafından desteklenir, bu iyileştirmeler isteyebilirsiniz. Genel olarak, ancak, çok büyük olasılıkla bunu yanı sıra denetim gerçekleştiren emin olmak için belirli denetimine geçerli olduğu gibi bu tekniklerin bir çeşit kapsayıcıları gibi uygulamak denemelisiniz.

Bu iyileştirmeler sayesinde birçoğu uygulayabilirsiniz [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md), [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfası.

### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX Denetim Sihirbazı OLE en iyi duruma getirme seçenekleri

|MFC ActiveX Denetim Sihirbazı'nda denetim ayarı|Eylem|Daha fazla bilgi|
|-------------------------------------------------------|------------|----------------------|
|**Görünür olduğunda etkinleştirme** onay kutusu|Temizle|[Kapatma etkinleştirin görünür seçeneği](../mfc/turning-off-the-activate-when-visible-option.md)|
|**Penceresiz etkinleştirme** onay kutusu|Seçim|[Penceresiz Etkinleştirme Sağlama](../mfc/providing-windowless-activation.md)|
|**Kesilmemiş bir cihaz bağlamı** onay kutusu|Seçim|[Kesilmemiş Bir Cihaz Bağlamı Kullanma](../mfc/using-an-unclipped-device-context.md)|
|**Titreşimsiz etkinleştirme** onay kutusu|Seçim|[Titreşimsiz Etkinleştirme Sağlama](../mfc/providing-flicker-free-activation.md)|
|**İşaretçi bildirimleri etkin olmadığında fare** onay kutusu|Seçim|[Devre Dışı İken Fare Etkileşimi Sağlama](../mfc/providing-mouse-interaction-while-inactive.md)|
|**Kod en iyi duruma getirilmiş** onay kutusu|Seçim|[Denetim Çizimini İyileştirme](../mfc/optimizing-control-drawing.md)|

Bu iyileştirmeler uygulamak üye işlevleri hakkında ayrıntılı bilgi için bkz: [COleControl](../mfc/reference/colecontrol-class.md).

Daha fazla bilgi için bkz.:

- [Kalıcılığı ve Başlatmayı İyileştirme](../mfc/optimizing-persistence-and-initialization.md)

- [Penceresiz Etkinleştirme Sağlama](../mfc/providing-windowless-activation.md)

- [Kapatma etkinleştirin görünür seçeneği](../mfc/turning-off-the-activate-when-visible-option.md)

- [Devre Dışı İken Fare Etkileşimi Sağlama](../mfc/providing-mouse-interaction-while-inactive.md)

- [Titreşimsiz Etkinleştirme Sağlama](../mfc/providing-flicker-free-activation.md)

- [Kesilmemiş Bir Cihaz Bağlamı Kullanma](../mfc/using-an-unclipped-device-context.md)

- [Denetim Çizimini İyileştirme](../mfc/optimizing-control-drawing.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

