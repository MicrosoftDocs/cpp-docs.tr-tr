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
ms.openlocfilehash: 4b2b35376fa5e870396bd54af2ada2748dd92bd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372359"
---
# <a name="help-files-winhelp"></a>Yardım Dosyaları (WinHelp)

Yardım desteği WinHelp türünü seçerek uygulamanıza eklediğinizde, aşağıdaki dosyalar oluşturulur **bağlama duyarlı Yardım** onay kutusunu ve sonra seçerek **WinHelp biçimi** içinde[Gelişmiş Özellikler](../mfc/reference/advanced-features-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*PROJNAME*.hpj|*PROJNAME*\hlp|Kaynak dosyaları|Programınızı veya denetimin Yardım dosyası oluşturmak için Yardım Derleyici tarafından kullanılan Yardım proje dosyası.|
|*PROJNAME*.rtf|*PROJNAME*\hlp|Yardım dosyaları|Düzenleyebileceğiniz şablonu konuları ve .hpj dosyanızı özelleştirme hakkında bilgi içerir.|
|*PROJNAME*.cnt|*PROJNAME*\hlp|Yardım dosyaları|Yapısını sağlayan **içeriği** Windows Yardımı'nda penceresi.|
|Makehelp.bat|*PROJNAME*|Kaynak dosyaları|Proje derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|
|Print.rtf|*PROJNAME*\hlp|Yardım dosyaları|Projeniz yazdırma desteği (varsayılan) içeriyorsa, oluşturuldu. İletişim kutuları ve yazdırma komutları açıklar.|
|*.bmp|*PROJNAME*\hlp|Kaynak Dosyalar|Görüntüler farklı oluşturulmuş Yardım dosyası konuları içerir.|

Seçerek WinHelp desteği olan bir MFC ActiveX denetimi projeye ekleyebilirsiniz **Oluştur Yardım dosyaları** içinde [uygulama ayarları](../mfc/reference/application-settings-mfc-activex-control-wizard.md) MFC ActiveX Denetim Sihirbazı'nı sekmesi. MFC ActiveX denetimi Yardım desteği eklediğinizde aşağıdaki dosyaları projenize eklenir:

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*PROJNAME*.hpj|*PROJNAME*\hlp|Kaynak dosyaları|Proje dosyası, programı veya denetim Yardım dosyası oluşturmak için Yardım Derleyici tarafından kullanılan.|
|*PROJNAME*.rtf|*PROJNAME*\hlp|Proje|Düzenleyebileceğiniz şablonu konuları ve .hpj dosyanızı özelleştirme hakkında bilgi içerir.|
|Makehelp.bat|*PROJNAME*|Kaynak dosyaları|Proje derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|
|Bullet.bmp|*PROJNAME*|Kaynak Dosyalar|Madde işaretli listeler temsil etmek için standart dosya Yardımı tarafından kullanılır.|

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)