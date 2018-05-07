---
title: Derleme görevleri dosyası projesi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-makefile-project"></a>Derleme Görevleri Dosyası Projesi Oluşturma

Derleme görevleri dosyası kullanarak komut satırından derleme mevcut bir kaynak kod projesini varsa, Visual Studio geliştirme ortamında Visual Studio IDE özelliklerinden gerçekleştirebileceğiniz bir projeye kapatma çeşitli yolları vardır. Bu makalede, Visual Studio'da IDE kodunuzda oluşturmak için varolan makefile kullanan derleme görevleri dosyası projesi oluşturmak açıklar. Alternatif olarak, kullanabileceğiniz **varolan kod dosyalarından yeni proje oluştur** kaynak kodunuzdan yerel MSBuild proje oluşturmak için Sihirbazı. Daha fazla bilgi için bkz: [nasıl yapılır: Varolan koddan C++ projesi oluşturma](how-to-create-a-cpp-project-from-existing-code.md). Visual Studio 2017 içinde başlayarak, ayrıca kullanabilirsiniz **Klasör Aç** yerel Visual Studio projeleri değilmiş gibi birkaç varolan yapı sistemler kullanabilir özelliğini. Daha fazla bilgi için bkz: [Klasör Aç Visual C++ projelerinde](non-msbuild-projects.md).

Açın ve kaynak kodunuzu, varolan derleme görevleri dosyası kullanarak oluşturmak için Visual Studio kullanmak için önce yeni bir proje derleme görevleri dosyası proje şablonu seçerek oluşturun. Sihirbaz, derleme görevleri dosyası tarafından kullanılan ortam ve komutları belirtmenize yardımcı olur. Bu proje sonra Visual Studio geliştirme ortamında kodunuzun oluşturmak için de kullanabilirsiniz.

Varsayılan olarak, derleme görevleri dosyası projesi hiçbir dosya Çözüm Gezgini'nde görüntüler. Derleme görevleri dosyası projesi projenin özellik sayfasındaki yansıtılır oluşturma ayarlarını belirtir.

Projede belirttiğiniz çıktı dosyasının, derleme komut dosyasının oluşturduğu ad üzerinde hiçbir etkisi yoktur; yalnızca bir amaç belirtir. Derleme görevleri dosyası hala yapı işlemi denetler ve yapı hedefleri belirtir.

## <a name="to-create-a-makefile-project"></a>Makefile projesi oluşturmak için

1. Yardım konusundaki yönergeleri izleyerek [proje bir Visual C++ Uygulama Sihirbazı oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md).

1. İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C++** > **genel** ve ardından **derleme görevleri dosyası projesi** içinde Proje Sihirbazı'nı açmak için Şablonlar bölmesinde.

1. İçinde [uygulama ayarları](../ide/application-settings-makefile-project-wizard.md) sayfasında, komut çıktısında, temizleyin ve yeniden bilgi için hata ayıklama ve perakende derlemeler sağlayın.

1. Tıklatın **son** Sihirbazı kapatmak ve yeni oluşturulan projede açmak için **Çözüm Gezgini**.

Özellik sayfasında projenin özelliklerini görüntüleyebilir ve düzenleyebilirsiniz. Bkz: [Visual C++ proje özelliklerini ayarlama](../ide/working-with-project-properties.md) özellik sayfası görüntüleme hakkında bilgi.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası Projesi Sihirbazı](../ide/makefile-project-wizard.md)<br/>
[Derleme Görevleri Dosyasındaki Özel Karakterler](../build/special-characters-in-a-makefile.md)<br/>
[Derleme Görevleri Dosyası İçeriği](../build/contents-of-a-makefile.md)<br/>
