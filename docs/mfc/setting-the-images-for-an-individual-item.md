---
title: Ayrı bir öğe için görüntüleri ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ddf2f3a57511e227a934f11262f46b528dc20aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373496"
---
# <a name="setting-the-images-for-an-individual-item"></a>Ayrı Bir Öğe için Görüntüleri Ayarlama

Genişletilmiş Birleşik giriş kutusu öğe tarafından kullanılan görüntüler farklı türde değerler tarafından belirlenir *iImage*, *iSelectedImage*, ve *IOverlay* üyeleri[ COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) yapısı. Her değer denetim ilişkili görüntü listesinden görüntü dizinidir. Varsayılan olarak, bu üyeler görüntü öğe için gösterilecek denetim neden 0 olarak ayarlanır. Belirli bir öğe için görüntüleri kullanmak istiyorsanız, yapı buna göre birleşik giriş kutusu öğesi eklerken ya da mevcut bir birleşik giriş kutusu öğesini değiştirerek değiştirebilirsiniz.

## <a name="setting-the-image-for-a-new-item"></a>Yeni bir öğe için görüntüsü ayarlama

Yeni bir öğe ekliyorsanız, başlatma *iImage*, *iSelectedImage*, ve *IOverlay* yapısı uygun değerlerle üyeleri ve sonra bir çağrı ile öğeyi ekleyin [CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem).

Aşağıdaki örnek yeni bir Genişletilmiş Birleşik giriş kutusu öğe ekler (`cbi`) Genişletilmiş Birleşik giriş kutusu denetimine (`m_comboEx`), üç durumları görüntü için dizinleri sağlama:

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>Var olan bir öğe için görüntüsü ayarlama

Var olan bir öğeye değiştiriyorsanız, çalışmanız için gereken *maskesi* üyesi bir **COMBOBOXEXITEM** yapısı.

#### <a name="to-modify-an-existing-item-to-use-images"></a>Görüntüleri kullanmak için bir varolan öğeyi değiştirmek için

1. Bildirme bir **COMBOBOXEXITEM** yapısı ve ayarlama *maskesi* değerlerine veri üyesi olduğunuz ilgilenen değiştirme.

1. Bu yapıyı kullanarak bir çağrı yapmak [CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem).

1. Değiştirme *maskesi*, *iImage*, ve *iSelectedImage* uygun değerleri kullanarak yeni döndürülen yapının üyeleri.

1. Çağrı yapmak [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem), değiştirilen yapısında geçen.

Aşağıdaki örnek, üçüncü Genişletilmiş Birleşik giriş kutusu öğesinin seçili ve seçili görüntüleri değiştirerek, bu yordamı gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

