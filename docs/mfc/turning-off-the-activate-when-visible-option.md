---
description: 'Hakkında daha fazla bilgi edinin: görünür olduğunda etkinleştir seçeneğini kapatma'
title: Görünürken Etkinleştir Seçeneğini Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: fcb5f7ef0518cbf257ef9ee7a659c9617092b7d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263874"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Görünürken Etkinleştir Seçeneğini Kapatma

Bir denetimin iki temel durumu vardır: etkin ve devre dışı. Geleneksel olarak, bu durumlar denetimin bir pencere içerip içermediğini ayırt etmişti. Etkin bir denetimde pencere vardı; etkin olmayan bir denetim değildi. Penceresiz etkinleştirmenin tanıtılmasıyla, bu ayrım artık evrensel değildir, ancak yine de birçok denetim için geçerli olur.

Genellikle ActiveX denetimi tarafından gerçekleştirilen başlatmanın geri kalanı ile karşılaştırıldığında, pencerenin oluşturulması son derece pahalı bir işlemdir. İdeal olarak, bir denetim kesinlikle gerekli olana kadar penceresini oluşturmayı erteler.

Birçok denetimin bir kapsayıcıda görünür oldukları sürenin tamamına etkin olması gerekmez. Genellikle, Kullanıcı etkin hale gelmesini gerektiren bir işlem gerçekleştirene kadar (örneğin, fareyle tıklanması veya sekme tuşuna basarak) bir denetim etkin olmayan durumda kalabilir. Kapsayıcının onu etkinleştirmesi gerekmediği sürece bir denetimin etkin kalmasını sağlamak için, denetimin çeşitli bayraklarından **OLEMISC_ACTIVATEWHENVISIBLE** bayrağını kaldırın:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

Denetiminizi oluştururken MFC ActiveX denetimi sihirbazının [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında **görünür olduğunda etkinleştir** seçeneğini kapatırsanız **OLEMISC_ACTIVATEWHENVISIBLE** bayrağı otomatik olarak atlanır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](../mfc/mfc-activex-controls-optimization.md)
