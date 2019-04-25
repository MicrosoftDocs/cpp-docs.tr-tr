---
title: Görünürken Etkinleştir Seçeneğini Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: a7afe9617aa356916fe184828d7684f228293e39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181503"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Görünürken Etkinleştir Seçeneğini Kapatma

Bir denetimi iki temel durum vardır: etkin ve etkin değil. Geleneksel olarak, bu durumları denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan bir denetim belirtmiyor. Penceresiz etkinleştirme tanıtımıyla Bu ayrım artık Evrensel değildir ancak yine de birçok denetim için geçerlidir.

Genellikle bir ActiveX denetimi tarafından gerçekleştirilen başlatma geri kalanı ile karşılaştırıldığında, bir pencere oluşturulmasını son derece pahalı bir işlemdir. İdeal olarak, bir denetimi kesinlikle gerekli kadar penceresi oluşturma erteleme.

Pek çok denetimi bir kapsayıcıda görünür oldukları tüm zaman etkin olması gerekmez. Genellikle, kullanıcı (örneğin fare ile tıklandığında veya SEKME tuşuna basarak) etkin olmasını gerektiren bir işlem başarılı olana dek denetim etkin olmayan bir durumda kalabilir. Bir denetimin, kapsayıcı etkinleştirmek gereken kadar devre dışı kalmasına neden için kaldırın **OLEMISC_ACTIVATEWHENVISIBLE** denetimin çeşitli bayrakları bayrağı:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

**OLEMISC_ACTIVATEWHENVISIBLE** bayrağı otomatik olarak devre dışı bırakırsanız atlanmış **etkinleştirme olduğunda görünür** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX sayfası Denetiminizi oluşturduğunuzda denetimi Sihirbazı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md)
