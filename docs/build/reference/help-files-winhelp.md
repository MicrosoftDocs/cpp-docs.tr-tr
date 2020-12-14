---
description: 'Hakkında daha fazla bilgi edinin: yardım dosyaları (WinHelp)'
title: Yardım Dosyaları (WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 77d00154db762d11e064fe91681b81fbe859e7be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200058"
---
# <a name="help-files-winhelp"></a>Yardım Dosyaları (WinHelp)

**Bağlama duyarlı yardım** onay kutusunu seçerek ve ardından MFC Uygulama sihirbazının [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında **WinHelp biçimi** ' ni seçerek uygulamanıza yardım desteğinin WinHelp türünü eklediğinizde aşağıdaki dosyalar oluşturulur.

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*ProjName*. hpj|*ProjName*\hlp|Kaynak dosyalar|Program veya denetiminizin yardım dosyasını oluşturmak için Yardım derleyicisi tarafından kullanılan yardım projesi dosyası.|
|*ProjName*. rtf|*ProjName*\hlp|Yardım dosyaları|Düzenleyebilmeniz için kullanabileceğiniz şablon konularını ve. hpj dosyanızı özelleştirme bilgilerini içerir.|
|*ProjName*. sayisi|*ProjName*\hlp|Yardım dosyaları|Windows Yardımı 'nda **içerikler** penceresi için yapı sağlar.|
|Makehelp.bat|*ProjName*|Kaynak dosyalar|Proje derlendiğinde yardım projesi oluşturmak için sistem tarafından kullanılır.|
|Print. rtf|*ProjName*\hlp|Yardım dosyaları|Projeniz yazdırma desteği (varsayılan) içeriyorsa oluşturulur. Yazdırma komutlarını ve iletişim kutularını açıklar.|
|*. bmp|*ProjName*\hlp|Kaynak Dosyalar|Oluşturulmuş farklı yardım dosyası konuları için görüntü içerir.|

MFC ActiveX Denetim Sihirbazı 'nın [uygulama ayarları](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) sekmesinde **Yardım dosyaları oluştur** ' a tıklayarak bir MFC ActiveX denetimi projesine WinHelp desteği ekleyebilirsiniz. MFC ActiveX denetimine yardım desteği eklediğinizde aşağıdaki dosyalar projenize eklenir:

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*ProjName*. hpj|*ProjName*\hlp|Kaynak dosyalar|Program veya denetiminizin yardım dosyasını oluşturmak için Yardım derleyicisi tarafından kullanılan proje dosyası.|
|*ProjName*. rtf|*ProjName*\hlp|Project|Düzenleyebilmeniz için kullanabileceğiniz şablon konularını ve. hpj dosyanızı özelleştirme bilgilerini içerir.|
|Makehelp.bat|*ProjName*|Kaynak dosyalar|Proje derlendiğinde yardım projesi oluşturmak için sistem tarafından kullanılır.|
|Bullet.bmp|*ProjName*|Kaynak Dosyalar|Madde işaretli listeleri temsil etmek için standart Yardım dosyası konuları tarafından kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)
