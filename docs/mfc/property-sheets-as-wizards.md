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
ms.openlocfilehash: 634359763f24e02987664fe3de1094e3e7fec64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="property-sheets-as-wizards"></a>Sihirbaz Olarak Özellik Sayfaları
Bir anahtar Sihirbazı özellik sayfası sekmeleri yerine İleri veya Son'u, geri ve İptal düğmeleri ile gezinti sağlanır özelliğidir. Çağırmanız gerekir [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) çağırmadan önce [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) bu özelliğin avantajlarından yararlanmak için özellik sayfası nesne üzerinde.  
  
 Aynı kullanıcının aldığı [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) ve [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) başka bir sayfaya bir sayfadan diğerine taşırken bildirimleri. Sonraki ve Son'u düğmeleri birbirini dışlayan denetimleridir; diğer bir deyişle, yalnızca bunlardan birinin aynı anda gösterilir. İlk sayfasında İleri düğmesi etkinleştirilmiş olmalıdır. Kullanıcı son sayfasında ise son düğmesine etkinleştirilmiş olmalıdır. Bu çerçevesi tarafından otomatik olarak yapılmamaktadır. Çağrılacak olan [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) Bunu başarmak için son sayfasında.  
  
 Tüm varsayılan düğmeleri görüntülemek için mush Son düğmesini göster ve İleri düğmesine taşıyın. İleri düğmesine göreli konumunu korunabilmesi için Geri'yi taşıyın.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)

