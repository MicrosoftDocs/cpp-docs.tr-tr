---
title: Ayrı Bir Öğe için Resimleri Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 177c06acfe665a43921b19407d9d357d4545e748
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511282"
---
# <a name="setting-the-images-for-an-individual-item"></a>Ayrı Bir Öğe için Resimleri Ayarlama

Genişletilmiş Birleşik giriş kutusu öğesi tarafından kullanılan farklı görüntü türleri, *IImage*, *ıselectedimage*ve [Comboboxexitem](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısının *IOverlay* üyelerinin değerleri tarafından belirlenir. Her değer, denetimin ilişkili görüntü listesindeki bir görüntünün dizinidir. Varsayılan olarak, bu Üyeler 0 olarak ayarlanır ve denetimin öğe için görüntü görüntülememesine neden olur. Belirli bir öğe için görüntüleri kullanmak istiyorsanız, Birleşik giriş kutusu öğesini eklerken ya da varolan bir Birleşik giriş kutusu öğesini değiştirerek yapıyı uygun şekilde değiştirebilirsiniz.

## <a name="setting-the-image-for-a-new-item"></a>Görüntüyü yeni bir öğe için ayarlama

Yeni bir öğe ekliyorsanız, *IImage*, *ıselectedimage*ve *IOverlay* yapısı üyelerini uygun değerlerle başlatın ve ardından bir [CComboBoxEx:: InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)çağrısı olan öğeyi ekleyin.

Aşağıdaki örnek, Genişletilmiş Birleşik giriş kutusu`cbi``m_comboEx`denetimine () yeni bir Genişletilmiş Birleşik giriş kutusu öğesi () ekler ve üç görüntü durumu için dizinler sağlayabilir:

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>Varolan bir öğe için görüntü ayarlanıyor

Varolan bir öğeyi değiştiriyorsanız, bir **COMBOBOXEXITEM** yapısının *maske* üyesiyle çalışmanız gerekir.

#### <a name="to-modify-an-existing-item-to-use-images"></a>Varolan bir öğeyi görüntüleri kullanmak üzere değiştirmek için

1. Bir **COMBOBOXEXITEM** yapısı bildirin ve *maske* verileri üyesini, değiştirmek istediğiniz değerlere ayarlayın.

1. Bu yapıyı kullanarak [CComboBoxEx:: GetItem](../mfc/reference/ccomboboxex-class.md#getitem)'a bir çağrı yapın.

1. Yeni döndürülen yapının *maskesini*, *IImage*ve *ıselectedimage* üyelerini uygun değerleri kullanarak değiştirin.

1. Değiştirilen yapıyı geçirerek [CComboBoxEx:: SetItem](../mfc/reference/ccomboboxex-class.md#setitem)öğesine bir çağrı yapın.

Aşağıdaki örnek, üçüncü Genişletilmiş Birleşik giriş kutusu öğesinin seçili ve seçilmemiş görüntülerini takas ederek bu yordamı gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
