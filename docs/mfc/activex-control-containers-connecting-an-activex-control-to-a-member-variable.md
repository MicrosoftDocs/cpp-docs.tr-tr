---
title: 'ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
ms.openlocfilehash: 620a9ec58b3a5a8fcdac63626b81fbc4620de399
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371613"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama

ActiveX denetimine denetim kapsayıcısı uygulaması içinden erişmesinin en kolay yolu, ActiveX denetimini denetimiçeren iletişim sınıfının bir üye değişkeniyle ilişkilendirmektir.

> [!NOTE]
> Bu, bir kapsayıcı sınıfı nın içinden katıştırılmış bir denetime erişmek için tek yol değildir, ancak bu makalenin amaçları için yeterlidir.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>İletişim sınıfına üye değişken ekleme

1. Sınıf Görünümü'nden, kısayol menüsünü açmak için ana iletişim sınıfına sağ tıklayın. Örneğin, `CContainerDlg`.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Değişken Ekle'yi**tıklatın.

1. Üye Değişken Ekle Sihirbazı'nda **Denetim değişkenini**tıklatın.

1. Denetim **Kimliği** liste kutusunda, gömülü ActiveX denetiminin denetim kimliğini seçin. Örneğin, `IDC_CIRCCTRL1`.

1. Değişken **Adı** kutusuna bir ad girin.

   Örneğin, *m_circctl.*

1. Seçimlerinizi kabul etmek ve Üye Değişken Ekle Sihirbazı'ndan çıkmak için **Bitir'i** tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Kontrol Kapları](../mfc/activex-control-containers.md)
