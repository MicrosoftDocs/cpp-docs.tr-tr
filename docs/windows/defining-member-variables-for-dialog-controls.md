---
title: "İletişim kutusu denetimleri için üye değişkenleri tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb966459695eb048943a12e33c8e909f99fdc92b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-member-variables-for-dialog-controls"></a>İletişim Kutusu Denetimleri İçin Üye Değişkenleri Tanımlama
Düğmeler dışındaki herhangi bir iletişim kutusu denetimi için bir üye değişkeni tanımlamak için aşağıdaki yöntemi kullanabilirsiniz.  
  
> [!NOTE]
>  Bu makale, yalnızca bir MFC projesine içinde iletişim kutusu denetimleri için geçerlidir. ATL projeleri kullanması gereken **yeni Windows iletileri ve olay işleyicileri** iletişim kutusu.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(Düğme olmayan) iletişim kutusu denetimi için bir üye değişkeni tanımlamak için  
  
1.  İçinde [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md), bir denetim seçin.  
  
2.  Tuşlarına basarak sırasında **CTRL** anahtar, iletişim kutusu denetimi çift tıklatın.  
  
     [Üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md) görüntülenir.  
  
3.  Uygun bilgileri yazın **üye değişkeni ekleme** Sihirbazı. Daha fazla bilgi için bkz: [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md).  
  
4.  Tıklatın **Tamam** iletişim kutusu Düzenleyicisi dönün.  
  
    > [!TIP]
    >  Hiçbir iletişim kutusu denetiminden varolan işleyicisine atlamak için denetimi çift tıklatın.  
  

  
 Aynı zamanda **üye değişkenleri** sekmesinde **MFC Sınıf Sihirbazı** belirli bir sınıf için yeni üye değişkenleri eklemek ve ve önceden tanımlanmış görüntülemek için.  
  
 Gereksinimler  
  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC Sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)

