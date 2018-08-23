---
title: Win32 Uygulama Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.appwiz.win32.overview
dev_langs:
- C++
helpviewer_keywords:
- Win32 Application Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdcd101759b35490451bf46bd6e222db469a3fba
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581248"
---
# <a name="win32-application-wizard"></a>Win32 Uygulama Sihirbazı

Visual C++ Win32 Uygulama Sihirbazı'nı (aşağıdaki tablonun başlığında listelenen) projeleri dört türlerinden herhangi birini oluşturmanıza olanak sağlar. Her durumda, açtığınız proje türü için uygun olan diğer seçenekler belirtebilirsiniz. Aşağıdaki tablo, her uygulama türü için kullanılabilir olan seçenekleri belirtir.

|Destek türü|Konsol uygulaması|Yürütülebilir (Windows) uygulama|Dinamik bağlantı kitaplığı|Statik kitaplık|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**Boş proje**|Evet|Evet|Evet|Hayır|
|**Sembolleri dışa aktarma**|Hayır|Hayır|Evet|Hayır|
|**Önceden derlenmiş üst bilgi**|Hayır|Hayır|Hayır|Evet|
|**ATL desteği**|Evet|Hayır|Hayır|Hayır|
|**MFC desteği**|Evet|Hayır|Hayır|Evet|

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturduğunuz Win32 uygulaması için geçerli proje ayarlarını açıklar. Varsayılan olarak, aşağıdaki seçenekleri ayarlıdır:

- Proje bir Windows uygulamasıdır.

- Proje boş değil.

- Proje dışa aktarma simgesi içerir.

- Proje (Bu seçenek yalnızca statik kitaplık projeleri için kullanılabilir) önceden derlenmiş üstbilgi dosyası kullanmaz.

- Proje MFC veya ATL için destek içerir.

Bu varsayılan ayarları değiştirmek için tıklayın [uygulama ayarları](../windows/application-settings-win-32-project-wizard.md) sekmesinde sihirbazın sol sütununda ve istediğiniz değişiklikleri yapın.

Windows masaüstü uygulaması oluşturduğunuzca genel C++ sınıflarını kullanarak ekleyebilirsiniz [genel](../ide/generic-cpp-class-wizard.md) kod Sihirbazı. HTML dosyaları, üstbilgi dosyaları, kaynaklar veya metin dosyaları gibi diğer öğeler ekleyebilirsiniz.

> [!NOTE]
> ATL sınıfları ekleyemezsiniz ve MFC desteği yalnızca bu Windows Masaüstü uygulama türleri için MFC sınıfları ekleyebilirsiniz (önceki tabloya bakın).

Projeniz için sihirbazın oluşturduğu dosyaları görüntüleyebilirsiniz **Çözüm Gezgini**. Projeniz için sihirbazın oluşturduğu dosyaları hakkında daha fazla bilgi için bkz: Proje tarafından oluşturulan dosya `ReadMe.txt`. Dosya türleri hakkında daha fazla bilgi için [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Boş Windows Masaüstü Uygulaması Oluşturma](../windows/creating-an-empty-windows-desktop-application.md)  
[Visual C++ proje türleri](../ide/visual-cpp-project-types.md)