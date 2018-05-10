---
title: Win32 Uygulama Sihirbazı'nı | Microsoft Docs
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
ms.openlocfilehash: 18885e36b5f598a8b1dd6128c29a9e520128dcb2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="win32-application-wizard"></a>Win32 Uygulama Sihirbazı
Visual C++ Win32 Uygulama Sihirbazı'nı (başlık aşağıdaki tabloda listelenen) projeleri dört türlerinden herhangi birini oluşturmanıza olanak sağlar. Her durumda, açtığınız proje türü için uygun olan diğer seçenekler belirtebilirsiniz. Aşağıdaki tabloda, hangi seçeneklerin her uygulama türü için kullanılabilir olduğunu gösterir.  
  
|Destek türü|Konsol uygulaması|Yürütülebilir dosya (Windows) uygulama|Dinamik bağlantı kitaplığı|Statik kitaplığı|  
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|  
|**Boş proje**|Evet|Evet|Evet|Hayır|  
|**Sembolleri dışa aktarma**|Hayır|Hayır|Evet|Hayır|  
|**Önceden derlenmiş üst bilgi**|Hayır|Hayır|Hayır|Evet|  
|**ATL desteği**|Evet|Hayır|Hayır|Hayır|  
|**MFC desteği**|Evet|Hayır|Hayır|Evet|  
  
## <a name="overview"></a>Genel Bakış  
 Bu sihirbaz sayfası oluşturmakta olduğunuz bir Win32 uygulaması için geçerli proje ayarları açıklanır. Varsayılan olarak, aşağıdaki seçenekleri ayarlanır:  
  
-   Bir Windows uygulaması projesidir.  
  
-   Proje boş değil.  
  
-   Proje yok verme simgeler içeriyor.  
  
-   Proje (Bu seçenek yalnızca statik kitaplık projeleri için kullanılabilir) bir önceden derlenmiş üst bilgi dosyasını kullanmaz.  
  
-   Proje MFC ne ATL destekler  
  
 Bu varsayılan değiştirmek için tıklatın. [uygulama ayarları](../windows/application-settings-win-32-project-wizard.md) sekmesinde Sihirbazı'nın sol sütunda ve istediğiniz değişiklikleri yapın.  
  
 Bir Windows masaüstü uygulaması oluşturduktan sonra kullanarak genel C++ sınıfları ekleyebilirsiniz [genel](../ide/generic-cpp-class-wizard.md) kod Sihirbazı. HTML dosyaları, üst bilgi dosyaları, kaynakları veya metin dosyaları gibi diğer öğeleri ekleyebilirsiniz.  
  
> [!NOTE]
>  ATL sınıfları ekleyemezsiniz ve MFC desteği yalnızca bu Windows Masaüstü uygulama türleri için MFC sınıfları ekleyebilirsiniz (önceki tabloya bakın).  
  
 Projenizde Sihirbazın oluşturduğu dosyalarda görüntüleyebilirsiniz **Çözüm Gezgini**. Projeniz için sihirbaz dosyaları hakkında daha fazla bilgi için project oluşturulan dosya ReadMe.txt bakın. Dosya türleri hakkında daha fazla bilgi için [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Boş Windows masaüstü uygulaması oluşturma](../windows/creating-an-empty-windows-desktop-application.md)   
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)