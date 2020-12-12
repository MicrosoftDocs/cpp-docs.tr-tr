---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: Iyileştirme'
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
ms.openlocfilehash: db7fc1f1bdcdc3a3ffbf3b14d1809806389f0862
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294112"
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX Denetimleri: İyileştirme

Bu makalede, daha iyi performans için ActiveX denetimlerinizi iyileştirmek üzere kullanabileceğiniz teknikler açıklanmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

[Görünür olduğunda etkinleştir seçeneğini devre dışı bırakma](turning-off-the-activate-when-visible-option.md) ve [devre dışı Iken fare etkileşimi sağlama](providing-mouse-interaction-while-inactive.md) konuları, etkinleştirilinceye kadar bir pencere oluşturmayan denetimleri ele alır. [Penceresiz etkinleştirme sağlayan](providing-windowless-activation.md) konu, etkinleştirildiklerinde bile hiçbir zaman bir pencere oluşturmayacak denetimleri ele alır.

Windows 'un OLE nesneleri için iki önemli Sakıncaı vardır: etkin olduğunda nesnelerin saydam veya dikdörtgen olmayan olmasını önler ve denetimlerin örneklenmesi ve görüntülenmesi için büyük bir ek yük ekler. Genellikle bir pencere oluşturmak, bir denetimin oluşturulma zamanının yüzde 60 ' ünü alır. Tek bir paylaşılan pencere (genellikle kapsayıcının) ve bazı gönderme kodları ile, bir denetim aynı pencere hizmetlerini genellikle performans kaybı olmadan alır. Bir pencerenin olması, nesne için genellikle gereksiz ek yüke neden olur.

Bazı iyileştirmeler, denetiminiz belirli kapsayıcılarda kullanıldığında performansı iyileştirmez. Örneğin, 1996 ' den önce yayınlanan kapsayıcılar penceresiz etkinleştirmeyi desteklemez, bu nedenle bu özelliğin uygulanması eski kapsayıcılarda bir avantaj sağlamaz. Ancak neredeyse her kapsayıcı kalıcılığı destekler, böylece denetiminizin Kalıcılık kodunu iyileştirmek, muhtemelen herhangi bir kapsayıcıdaki performansını iyileştirir. Denetiminiz özellikle belirli bir kapsayıcı türüyle kullanılmak üzere tasarlanmışsa, bu iyileştirmelerin bu kapsayıcı tarafından desteklendiğini araştırmak isteyebilirsiniz. Ancak, genel olarak, denetiminizin çok sayıda kapsayıcı içinde de yapılabilmesini sağlamak için, belirli denetiminiz için geçerli olacak şekilde, bu tekniklerin çoğunu uygulamayı denemeniz gerekir.

Bu iyileştirmelerin birçoğunu, [denetim ayarları](reference/control-settings-mfc-activex-control-wizard.md) sayfasında [MFC ActiveX Denetim Sihirbazı](reference/mfc-activex-control-wizard.md)aracılığıyla uygulayabilirsiniz.

### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX denetimi Sihirbazı OLE Iyileştirme seçenekleri

|MFC ActiveX denetimi sihirbazında denetim ayarı|Eylem|Daha fazla bilgi|
|-------------------------------------------------------|------------|----------------------|
|**Görünür olduğunda etkinleştir** onay kutusu|Temizle|[Görünür olduğunda etkinleştir seçeneğini kapatma](turning-off-the-activate-when-visible-option.md)|
|**Penceresiz etkinleştirme** onay kutusu|Şunu seçin:|[Penceresiz etkinleştirme sağlama](providing-windowless-activation.md)|
|**Kırpılmamış cihaz bağlamı** onay kutusu|Şunu seçin:|[Kırpılmamış bir cihaz bağlamı kullanma](using-an-unclipped-device-context.md)|
|**Titreşimsiz etkinleştirme** onay kutusu|Şunu seçin:|[Flicker-Free etkinleştirme sağlama](providing-flicker-free-activation.md)|
|**Etkin olmadığında fare işaretçisi bildirimleri** onay kutusu|Şunu seçin:|[Devre dışı Iken fare etkileşimi sağlama](providing-mouse-interaction-while-inactive.md)|
|**İyileştirilmiş çizim kodu** onay kutusu|Şunu seçin:|[Denetim çizimini iyileştirme](optimizing-control-drawing.md)|

Bu iyileştirmeleri uygulayan üye işlevleri hakkında ayrıntılı bilgi için bkz. [Coelcontrol](reference/colecontrol-class.md).

Daha fazla bilgi için bkz:

- [Kalıcılığı ve başlatmayı iyileştirme](optimizing-persistence-and-initialization.md)

- [Penceresiz etkinleştirme sağlama](providing-windowless-activation.md)

- [Görünür olduğunda etkinleştir seçeneğini kapatma](turning-off-the-activate-when-visible-option.md)

- [Devre dışı Iken fare etkileşimi sağlama](providing-mouse-interaction-while-inactive.md)

- [Flicker-Free etkinleştirme sağlama](providing-flicker-free-activation.md)

- [Kırpılmamış bir cihaz bağlamı kullanma](using-an-unclipped-device-context.md)

- [Denetim çizimini iyileştirme](optimizing-control-drawing.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
