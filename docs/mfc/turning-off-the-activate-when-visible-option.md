---
title: Görünürken etkinleştir seçeneğini kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cb585496e6acf1c0ad94a43500e6d9a4830a2ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381289"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Görünürken Etkinleştir Seçeneğini Kapatma

Bir denetimi iki temel durum vardır: etkin ve etkin değil. Geleneksel olarak, bu durumları denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan bir denetim belirtmiyor. Penceresiz etkinleştirme tanıtımıyla Bu ayrım artık Evrensel değildir ancak yine de birçok denetim için geçerlidir.

Genellikle bir ActiveX denetimi tarafından gerçekleştirilen başlatma geri kalanı ile karşılaştırıldığında, bir pencere oluşturulmasını son derece pahalı bir işlemdir. İdeal olarak, bir denetimi kesinlikle gerekli kadar penceresi oluşturma erteleme.

Pek çok denetimi bir kapsayıcıda görünür oldukları tüm zaman etkin olması gerekmez. Genellikle, kullanıcı (örneğin fare ile tıklandığında veya SEKME tuşuna basarak) etkin olmasını gerektiren bir işlem başarılı olana dek denetim etkin olmayan bir durumda kalabilir. Bir denetimin, kapsayıcı etkinleştirmek gereken kadar devre dışı kalmasına neden için kaldırın **OLEMISC_ACTIVATEWHENVISIBLE** denetimin çeşitli bayrakları bayrağı:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

**OLEMISC_ACTIVATEWHENVISIBLE** bayrağı otomatik olarak devre dışı bırakırsanız atlanmış **etkinleştirme olduğunda görünür** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX sayfası Denetiminizi oluşturduğunuzda denetimi Sihirbazı.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

