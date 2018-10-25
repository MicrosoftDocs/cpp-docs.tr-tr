---
title: MFC uygulaması oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec61db21b27ef49f660751605b4788599f7f3485
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062502"
---
# <a name="creating-an-mfc-application"></a>MFC Uygulaması Oluşturma

Bir MFC uygulaması, Microsoft Foundation Class (MFC) kitaplığına dayalı Windows için yürütülebilir bir uygulamadır. Bir MFC uygulaması oluşturmak için en kolay yolu MFC Uygulama Sihirbazı'nı kullanmaktır.

> [!IMPORTANT]
>  MFC projeleri Visual Studio Express sürümlerinde desteklenmez.

MFC yürütülebilir dosyaları genelde beş türe ayrılır ayrılır: standart Windows uygulamaları, iletişim kutuları, form tabanlı uygulamalar, Explorer stilinde uygulamalar ve Web tarayıcısı stilinde uygulamalar. Daha fazla bilgi için bkz.:

- [Windows uygulamaları yazmak için sınıfları kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [İletişim Kutuları Oluşturma ve Görüntüleme](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Form Tabanlı MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Dosya Gezgini Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC Uygulama Sihirbazı uygun sınıf ve tüm uygulamalar, sihirbazda seçtiğiniz seçeneklere bağlı olarak bu tür dosyaları oluşturur.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı'nı kullanarak bir MFC uygulaması oluşturmak için

1. Yardım konusundaki yönergeleri izleyerek [Visual C++ uygulama sihirbazıyla proje oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md).

1. İçinde **yeni proje** iletişim kutusunda **MFC uygulaması** sihirbazını açmak için şablonlar bölmesindeki.

1. Kullanarak uygulama ayarlarınızı tanımlayın [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Sihirbaz tutmak için bu adımı atlayın varsayılan ayarlar.

1. Tıklayın **son** sihirbazı kapatın ve geliştirme ortamında yeni projenizi açın.

Projeniz oluşturulduktan sonra oluşturulan dosyalar görüntüleyebileceğiniz **Çözüm Gezgini**. Projeniz için sihirbaz dosyaları hakkında daha fazla bilgi için proje tarafından oluşturulan ReadMe.txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual C++ projeleri için oluşturulan dosya türleri](../../ide/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../ide/property-pages-visual-cpp.md)

