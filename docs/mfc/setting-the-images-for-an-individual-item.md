---
title: Ayrı bir öğe için resimleri ayarlama | Microsoft Docs
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
ms.openlocfilehash: b7f3dbdf4d386e40802d74459dd2854035b5b7c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380607"
---
# <a name="setting-the-images-for-an-individual-item"></a>Ayrı Bir Öğe için Görüntüleri Ayarlama
Genişletilmiş Birleşik giriş kutusu öğesi tarafından kullanılan görüntüleri farklı türde değerler tarafından belirlenir `iImage`, **iSelectedImage**, ve **IOverlay** üyeleri [COMBOBOXEXITEM ](http://msdn.microsoft.com/library/windows/desktop/bb775746) yapısı. Her değer denetim ilişkili görüntü listesinden görüntü dizinidir. Varsayılan olarak, bu üyeler öğesi için resim görüntülemek üzere denetimi neden 0 olarak ayarlanır. Belirli bir öğe için görüntüleri kullanmak istiyorsanız, yapısı buna birleşik giriş kutusu öğesi eklerken ya da var olan bir birleşik giriş kutusu öğesini değiştirerek değiştirebilirsiniz.  
  
## <a name="setting-the-image-for-a-new-item"></a>Yeni bir öğe için resmin ayarlama  
 Yeni bir öğe ekliyorsanız, başlatma `iImage`, **iSelectedImage**, ve **IOverlay** yapısı uygun değerlerle üyeleri ve ardından bir çağrı ile öğe ekleme [ CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem).  
  
 Aşağıdaki örnek yeni bir Genişletilmiş Birleşik giriş kutusu öğesi ekler (`cbi`) Genişletilmiş Birleşik giriş kutusu denetimine (`m_comboEx`), tüm üç durumları görüntü için dizinlerini sağladığını:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]  
  
## <a name="setting-the-image-for-an-existing-item"></a>Var olan bir öğe için resmin ayarlama  
 Varolan öğeyi değiştiriyorsanız, çalışmanız için gereken **maskesi** üyesi bir **COMBOBOXEXITEM** yapısı.  
  
#### <a name="to-modify-an-existing-item-to-use-images"></a>Görüntüleri kullanmak için varolan öğeyi değiştirmek için  
  
1.  Bildirme bir **COMBOBOXEXITEM** yapısı ve ayarlama **maskesi** değerlerine veri üyesi olduğunuz değiştirme ilgilenen.  
  
2.  Bu yapı kullanarak yaptığınız yapılan bir çağrı [CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem).  
  
3.  Değiştirme **maskesi**, `iImage`, ve **iSelectedImage** yeni döndürülen yapısı, uygun değerleri kullanarak üyeleri.  
  
4.  Çağırmaya [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem), değiştirilmiş yapısındaki geçen.  
  
 Aşağıdaki örnek, üçüncü Genişletilmiş Birleşik giriş kutusu öğesi seçili ve seçili görüntülerini takas tarafından bu yordamı gösterir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComboBoxEx kullanma](../mfc/using-ccomboboxex.md)   
 [Denetimler](../mfc/controls-mfc.md)

