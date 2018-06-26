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
ms.openlocfilehash: b3aa243ab8c0fb49e20e5b7485acdcd8bb808831
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930474"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama
Kendi denetim kapsayıcısı uygulamasına içinde bir ActiveX denetimi erişmek için kolay denetimi içerecek iletişim kutusu sınıfı ile bir üye değişkenine ActiveX denetimi ilişkilendirilecek yoludur.  
  
> [!NOTE]
>  Bu katıştırılmış bir denetimden kapsayıcı sınıfı içinde erişmek için tek yolu değildir, ancak bu makalenin amacıyla yeterli olur.  
  
### <a name="adding-a-member-variable-to-the-dialog-class"></a>İletişim kutusu sınıfı üye değişkeni ekleme  
  
1.  Sınıf görünümünden kısayol menüsünü açmak için ana iletişim sınıfı sağ tıklatın. Örneğin, `CContainerDlg`.  
  
2.  Kısayol menüsünden tıklatın **Ekle** ve ardından **değişken Ekle**.  
  
3.  Ekleme üye değişkeni Sihirbazı'nda tıklatın **denetim değişkeni**.  
  
4.  İçinde **denetim kimliği** liste kutusunda, katıştırılmış ActiveX denetiminin denetim kimliği seçin. Örneğin, `IDC_CIRCCTRL1`.  
  
5.  İçinde **değişken adı** kutusunda, bir ad girin.  
  
     Örneğin, *m_circctl*.  
  
6.  Tıklatın **son** seçimlerinizi kabul etmek ve ekleme üye değişkeni sihirbazdan çıkmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

