---
title: Ayrı Bir Öğe için Resimleri Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 39aa4761dbc753c42f1aedbb18f1832eab471e50
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294713"
---
# <a name="setting-the-images-for-an-individual-item"></a>Ayrı Bir Öğe için Resimleri Ayarlama

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

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
