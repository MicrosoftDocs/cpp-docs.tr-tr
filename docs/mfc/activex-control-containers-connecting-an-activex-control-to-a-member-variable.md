---
title: 'ActiveX denetim kapsayıcıları: bir üye değişkenine ActiveX denetimi bağlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6fed56e21f2b5d97b9b89596630cd63f544148
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078693"
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

