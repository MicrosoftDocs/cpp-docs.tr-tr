---
title: Yardım dosyaları (WinHelp) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 505506c7f3a14a73c6b0c859a70938fee3eed69e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
|*PROJNAME*.rtf|*PROJNAME*\hlp|Proje|Düzenleyebileceğiniz şablonu konuları ve .hpj dosyanızı özelleştirme hakkında bilgi içerir.|  
|Makehelp.bat|*PROJNAME*|Kaynak dosyaları|Projesi derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|  
|Bullet.bmp|*PROJNAME*|Kaynak Dosyalar|Madde işaretli listeler göstermek için standart dosya Yardımı tarafından kullanılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)