---
title: Sihirbaz olarak özellik sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73b6b0462012fc54b3bd6f2cb22422f5b1431288
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374216"
---
# <a name="property-sheets-as-wizards"></a>Sihirbaz Olarak Özellik Sayfaları

Bir anahtar bir sihirbaz özellik sayfası gezinme sekmeleri yerine sonraki veya Son'a geri ve İptal düğmeleri sağlanır özelliğidir. Çağırmanız gerekir [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) çağırmadan önce [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) üzerinde bu özellikten yararlanmak için özellik sayfası nesnesi.

Aynı kullanıcının aldığı [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) ve [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) başka bir sayfaya bir sayfadan taşırken bildirimleri. Sonraki ve bitiş düğmeleri birbirini dışlayan denetimlerdir; diğer bir deyişle, yalnızca bunlardan birinin aynı anda gösterilir. İlk sayfasında İleri düğmesi etkinleştirilmesi gerekir. Kullanıcının son sayfasında, son düğmesini etkinleştirilmesi gerekir. Bu çerçeve tarafından otomatik olarak yapılmaz. Çağırmak zorunda [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) Bunu başarmak için son sayfasında.

Tüm varsayılan düğmeleri görüntülemek için mush Son düğmesini göster ve İleri düğmesine taşıyın. Ardından İleri düğmesine göreli konumunu sürdürülmesi geri düğmesine taşıyın.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)

