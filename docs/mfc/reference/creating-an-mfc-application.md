---
title: MFC Uygulaması Oluşturma
ms.date: 07/28/2019
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 454a994da6db2841317d41ea1cdacfd36b0705e4
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606471"
---
# <a name="creating-an-mfc-application"></a>MFC Uygulaması Oluşturma

MFC uygulaması, Microsoft Foundation Class (MFC) kitaplığı 'nı temel alan Windows için yürütülebilir bir uygulamadır. MFC uygulaması oluşturmanın en kolay yolu MFC Uygulama Sihirbazı 'Nı kullanmaktır (Visual Studio 2019 ' de**MFC Uygulama Projesi** ). Bir MFC konsol uygulaması oluşturmak için, Windows Masaüstü Sihirbazı 'Nı kullanın ve **konsol uygulaması** ve **MFC üstbilgileri** seçeneklerini belirleyin.

> [!IMPORTANT]
>  MFC projeleri Visual Studio Express sürümlerde desteklenmez.

MFC yürütülebilir dosyaları genellikle beş türe ayrılır: standart Windows uygulamaları, iletişim kutuları, form tabanlı uygulamalar, Gezgin stili uygulamalar ve Web tarayıcı stili uygulamalar. Daha fazla bilgi için bkz.:

- [Windows uygulamaları yazmak için sınıfları kullanma](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [İletişim Kutuları Oluşturma ve Görüntüleme](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Form Tabanlı MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Dosya Gezgini Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC Uygulama Sihirbazı, sihirbazda belirlediğiniz seçeneklere bağlı olarak, bu tür uygulamalardan herhangi biri için uygun sınıfları ve dosyaları oluşturur.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı 'Nı kullanarak bir MFC uygulaması oluşturmak için

1. Konsol uygulaması projesi oluşturma yardım konusundaki yönergeleri izleyin. [ C++ ](../../get-started/tutorial-console-cpp.md)

1. **Yeni proje** iletişim kutusunda, Sihirbazı açmak için şablonlar bölmesindeki **MFC uygulaması** ' nı seçin.

1. [MFC Uygulama Sihirbazı 'nı](../../mfc/reference/mfc-application-wizard.md)kullanarak uygulama ayarlarınızı tanımlayın.

    > [!NOTE]
    >  Sihirbazın varsayılan ayarlarını korumak için bu adımı atlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın ve yeni projenizi geliştirme ortamında açın.

Projeniz oluşturulduktan sonra, **Çözüm Gezgini**oluşturulan dosyaları görüntüleyebilirsiniz. Sihirbazın projeniz için oluşturduğu dosyalar hakkında daha fazla bilgi için, proje tarafından oluşturulan ReadMe. txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual Studio C++ projeleri Için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)

