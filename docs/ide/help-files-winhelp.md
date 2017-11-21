---
title: "Yardım dosyaları (WinHelp) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a5036aa329c0b4004bd7ada724c62e1a1669f050
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="help-files-winhelp"></a>Yardım Dosyaları (WinHelp)
Yardım desteği WinHelp türünü seçerek uygulamanızı eklediğinizde, aşağıdaki dosyalar oluşturulur **bağlama duyarlı Yardım** onay kutusunu ve ardından seçerek **WinHelp biçimi** içinde[Gelişmiş Özellikler](../mfc/reference/advanced-features-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.  
  
|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|  
|---------------|------------------------|--------------------------------|-----------------|  
|*PROJNAME*.hpj|*PROJNAME*\hlp|Kaynak dosyaları|Yardım Derleyici tarafından programınız veya denetimin Yardım dosyası oluşturmak için kullanılan Yardım proje dosyası.|  
|*PROJNAME*.rtf|*PROJNAME*\hlp|Yardım dosyaları|Düzenleyebileceğiniz şablonu konuları ve .hpj dosyanızı özelleştirme hakkında bilgi içerir.|  
|*PROJNAME*.cnt|*PROJNAME*\hlp|Yardım dosyaları|Yapısını sağlar **içeriği** Windows Yardım penceresinde.|  
|Makehelp.bat|*PROJNAME*|Kaynak dosyaları|Projesi derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|  
|Print.rtf|*PROJNAME*\hlp|Yardım dosyaları|Projenizi yazdırma desteği (varsayılan) içeriyorsa oluşturulur. Yazdırma komutlarını ve iletişim kutuları açıklar.|  
|*.bmp|*PROJNAME*\hlp|Kaynak Dosyalar|Görüntüler için farklı oluşturulan Yardım dosyası konuları içerir.|  
  
 Seçerek bir MFC ActiveX denetimi projesine WinHelp destek ekleyebilirsiniz **Generate Yardım dosyalarını** içinde [uygulama ayarları](../mfc/reference/application-settings-mfc-activex-control-wizard.md) MFC ActiveX Denetim Sihirbazı'nı sekmesinde. MFC ActiveX denetimi Yardım desteği eklediğinizde aşağıdaki dosyaları projenize eklenir:  
  
|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|  
|---------------|------------------------|--------------------------------|-----------------|  
|*PROJNAME*.hpj|*PROJNAME*\hlp|Kaynak dosyaları|Yardım Derleyici tarafından programınızı veya denetimin Yardım dosyası oluşturmak için kullanılan proje dosyası.|  
|*PROJNAME*.rtf|*PROJNAME*\hlp|Project|Düzenleyebileceğiniz şablonu konuları ve .hpj dosyanızı özelleştirme hakkında bilgi içerir.|  
|Makehelp.bat|*PROJNAME*|Kaynak dosyaları|Projesi derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|  
|Bullet.bmp|*PROJNAME*|Kaynak Dosyalar|Madde işaretli listeler göstermek için standart dosya Yardımı tarafından kullanılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)