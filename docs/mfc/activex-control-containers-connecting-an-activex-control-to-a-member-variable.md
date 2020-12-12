---
description: 'Daha fazla bilgi edinin: ActiveX denetim kapsayıcıları: bir ActiveX denetimini üye değişkenine bağlama'
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
ms.openlocfilehash: c3b890b5705624a18ec42583b143fbd33e4f0608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271908"
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
