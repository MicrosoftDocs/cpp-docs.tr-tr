---
title: "ActiveX denetim kapsayıcıları: bir üye değişkenine ActiveX denetimi bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2248dd68b0ecc7471899552bcb7b0394f3f9f363
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
     Örneğin, `m_circctl`.  
  
6.  Tıklatın **son** seçimlerinizi kabul etmek ve ekleme üye değişkeni sihirbazdan çıkmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

