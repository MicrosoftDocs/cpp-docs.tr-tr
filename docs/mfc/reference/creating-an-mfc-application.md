---
title: MFC Uygulaması Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 251275fd866ce7c9d697787c35c6207ef77862db
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818602"
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

1. Yardım konusundaki yönergeleri izleyerek [C++ konsol uygulama projesi oluşturma](../../get-started/tutorial-console-cpp.md).

1. İçinde **yeni proje** iletişim kutusunda **MFC uygulaması** sihirbazını açmak için şablonlar bölmesindeki.

1. Kullanarak uygulama ayarlarınızı tanımlayın [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Sihirbaz tutmak için bu adımı atlayın varsayılan ayarlar.

1. Tıklayın **son** sihirbazı kapatın ve geliştirme ortamında yeni projenizi açın.

Projeniz oluşturulduktan sonra oluşturulan dosyalar görüntüleyebileceğiniz **Çözüm Gezgini**. Projeniz için sihirbaz dosyaları hakkında daha fazla bilgi için proje tarafından oluşturulan ReadMe.txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual C++ projeleri için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)

