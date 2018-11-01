---
title: Sihirbaz Olarak Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: e8ba740d31681de214d2a497bc2694a94d09d84d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542629"
---
# <a name="property-sheets-as-wizards"></a>Sihirbaz Olarak Özellik Sayfaları

Bir anahtar bir sihirbaz özellik sayfası gezinme sekmeleri yerine sonraki veya Son'a geri ve İptal düğmeleri sağlanır özelliğidir. Çağırmanız gerekir [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) çağırmadan önce [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) üzerinde bu özellikten yararlanmak için özellik sayfası nesnesi.

Aynı kullanıcının aldığı [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) ve [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) başka bir sayfaya bir sayfadan taşırken bildirimleri. Sonraki ve bitiş düğmeleri birbirini dışlayan denetimlerdir; diğer bir deyişle, yalnızca bunlardan birinin aynı anda gösterilir. İlk sayfasında İleri düğmesi etkinleştirilmesi gerekir. Kullanıcının son sayfasında, son düğmesini etkinleştirilmesi gerekir. Bu çerçeve tarafından otomatik olarak yapılmaz. Çağırmak zorunda [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) Bunu başarmak için son sayfasında.

Tüm varsayılan düğmeleri görüntülemek için mush Son düğmesini göster ve İleri düğmesine taşıyın. Ardından İleri düğmesine göreli konumunu sürdürülmesi geri düğmesine taşıyın.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)

