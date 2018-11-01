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
ms.openlocfilehash: 2234647e933e37ff82845c4b40dc93cefeb55575
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446469"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama

ActiveX denetimi denetimi içeren bir iletişim kutusu sınıfı üyesi değişkeninin ile ilişkilendirmek için Denetim kapsayıcılı bir uygulama içinde ActiveX denetiminden erişmek için en kolay yolu var.

> [!NOTE]
>  Bu katıştırılmış bir denetimden kapsayıcı sınıfı içinde erişmenin tek yolu değildir, ancak bu makalenin amaçları için yeterli olur.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>İletişim kutusu sınıfı için bir üye değişkeni ekleme

1. Sınıf Görünümü, ana iletişim kutusu sınıfı, kısayol menüsünü açmak için sağ tıklayın. Örneğin: `CContainerDlg`

1. Kısayol menüsünden tıklayın **Ekle** ardından **değişken Ekle**.

1. Ekleme üye değişkeni Sihirbazı'nda tıklatın **denetim değişkeni**.

1. İçinde **denetim kimliği** liste kutusunda, katıştırılmış ActiveX denetiminin denetim Kimliğini seçin. Örneğin: `IDC_CIRCCTRL1`

1. İçinde **değişken adı** kutusunda, bir ad girin.

   Örneğin, *m_circctl*.

1. Tıklayın **son** seçimlerinizi kabul etmek ve ekleme üye değişkeni sihirbazdan çıkmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

