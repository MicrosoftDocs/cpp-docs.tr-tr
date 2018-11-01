---
title: Görünürken Etkinleştir Seçeneğini Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: 42dbec7a55085235e43fa14ab6406bfb3526afdb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464837"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Görünürken Etkinleştir Seçeneğini Kapatma

Bir denetimi iki temel durum vardır: etkin ve etkin değil. Geleneksel olarak, bu durumları denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan bir denetim belirtmiyor. Penceresiz etkinleştirme tanıtımıyla Bu ayrım artık Evrensel değildir ancak yine de birçok denetim için geçerlidir.

Genellikle bir ActiveX denetimi tarafından gerçekleştirilen başlatma geri kalanı ile karşılaştırıldığında, bir pencere oluşturulmasını son derece pahalı bir işlemdir. İdeal olarak, bir denetimi kesinlikle gerekli kadar penceresi oluşturma erteleme.

Pek çok denetimi bir kapsayıcıda görünür oldukları tüm zaman etkin olması gerekmez. Genellikle, kullanıcı (örneğin fare ile tıklandığında veya SEKME tuşuna basarak) etkin olmasını gerektiren bir işlem başarılı olana dek denetim etkin olmayan bir durumda kalabilir. Bir denetimin, kapsayıcı etkinleştirmek gereken kadar devre dışı kalmasına neden için kaldırın **OLEMISC_ACTIVATEWHENVISIBLE** denetimin çeşitli bayrakları bayrağı:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

**OLEMISC_ACTIVATEWHENVISIBLE** bayrağı otomatik olarak devre dışı bırakırsanız atlanmış **etkinleştirme olduğunda görünür** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX sayfası Denetiminizi oluşturduğunuzda denetimi Sihirbazı.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

