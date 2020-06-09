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
ms.openlocfilehash: 87cb560a1054a912a4e8574cfe2dee74d5e61fe6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625140"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama

Bir ActiveX denetimine denetim kapsayıcısı uygulamasının içinden erişmenin en kolay yolu, ActiveX denetimini denetimi içerecek iletişim kutusu sınıfının bir üye değişkeniyle ilişkilendirmenize olanak sağlar.

> [!NOTE]
> Bu, bir kapsayıcı sınıfından eklenmiş bir denetime erişmenin tek yolu değildir, ancak bu makalenin amaçları doğrultusunda yeterlidir.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>İletişim sınıfına üye değişkeni ekleme

1. Sınıf Görünümü, kısayol menüsünü açmak için ana iletişim kutusu sınıfına sağ tıklayın. Örneğin, `CContainerDlg`.

1. Kısayol menüsünde, **Ekle** ' ye tıklayın ve ardından **değişken ekleyin**.

1. Üye değişkeni Ekleme sihirbazında **denetim değişkeni**' ne tıklayın.

1. **DENETIM kimliği** liste kutusunda, katıştırılmış ActiveX DENETIMININ denetim kimliğini seçin. Örneğin, `IDC_CIRCCTRL1`.

1. **Değişken adı** kutusuna bir ad girin.

   Örneğin, *m_circctl*.

1. Seçimlerinizi kabul etmek ve üye değişkeni ekleme sihirbazından çıkmak için **son** ' a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX denetim kapsayıcıları](activex-control-containers.md)
