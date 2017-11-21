---
title: "İletişim kutusu denetimleri ile kod arasında geçiş yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 831b8ca3eddec1bfd13d166d98454206bfac1bfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="switching-between-dialog-box-controls-and-code"></a>İletişim Kutusu Denetimleri ile Kod Arasında Geçiş Yapma
MFC uygulamalarında üzerine iletişim kutusu denetimleri saplama işleyici işlevleri hızlı bir şekilde oluşturmak için veya kendi işleyici kodu atlamak için çift tıklayın.  
  
 Seçili bir denetimi ile **ControlEvents'i** düğmesini veya **iletileri** düğmesini [Özellikler penceresini](/visualstudio/ide/reference/properties-window) Windows iletileri ve olayları tam bir listesini görüntülemek için Seçilen öğe için kullanılabilir. Oluşturmak veya işleyici işlevleri düzenlemek için listeden seçin.  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>İletişim kutusu Düzenleyicisi'nden kod atlamak için  
  
1.  En son uygulanan kendi ileti işlevi işleme bildirimi atlamak için iletişim kutusu denetimine çift tıklayın. (ATL tabanlı iletişim sınıfları için her zaman Oluşturucusu tanımına atlamak.)  
  
### <a name="to-view-events-for-a-control"></a>Bir denetim olaylarını görüntülemek için  
  
1.  Seçili bir denetimi ile **ControlEvents'i** düğmesini [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
    > [!NOTE]
    >  Tıklatarak **ControlEvents'i** ne zaman düğmesini *iletişim kutusu* odak çıkarır sonra ayrı ayrı denetimler için olayları düzenlemek için genişletebilirsiniz iletişim kutusundaki tüm denetimler listesine sahip.  
  
     Tek bir denetim iletişim kutusunda odağa sahip olduğunda, sağ tıklatın ve seçin **olay işleyicisi ekleme** kısayol menüsünden. Bu işleyici ekleneceği sınıfı belirtmenize olanak sağlar. Daha fazla bilgi için bkz: [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).  
  
### <a name="to-view-messages-for-a-dialog-box"></a>Bir iletişim kutusu iletilerini görüntülemek için  
  
1.  İletişim kutusu seçili tıklatın **iletileri** düğmesini [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)

