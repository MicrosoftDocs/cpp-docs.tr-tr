---
description: 'Hakkında daha fazla bilgi edinin: sihirbaz olarak özellik sayfaları'
title: Sihirbaz Olarak Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: 2a68a16936e8ab134bab2fe78dac0d29c125b4db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248872"
---
# <a name="property-sheets-as-wizards"></a>Sihirbaz Olarak Özellik Sayfaları

Sihirbaz Özellik sayfasının temel bir özelliği, sekmeler yerine Ileri veya bitiş, geri ve Iptal düğmeleri ile gezintinin sağlandır. Bu özellikten yararlanabilmek için CPropertySheet: [: SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) : Özellik sayfası nesnesindeki [:D omodal](../mfc/reference/cpropertysheet-class.md#domodal) ' i çağırmanız gerekir.

Kullanıcı bir sayfadan diğerine taşınırken aynı [CPropertyPage:: OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) ve [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) bildirimlerini alır. İleri ve son düğmeleri birbirini dışlamalı denetimlerdir; diğer bir deyişle, tek seferde bunlardan yalnızca biri gösterilir. İlk sayfada, Ileri düğmesi etkinleştirilmelidir. Kullanıcı son sayfaalıyorsa, son düğmesi etkinleştirilmelidir. Bu, çerçeve tarafından otomatik olarak yapılmaz. Bunu başarmak için son sayfada [CPropertySheet:: SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) öğesini çağırmanız gerekir.

Tüm varsayılan düğmeleri görüntülemek için, son düğmesini gösterin ve Ileri düğmesini hareket ettirin. Ardından geri düğmesini, göreli konumunun Ileri düğmesine sahip olacak şekilde taşıyın.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
