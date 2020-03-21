---
title: MFC DLL Projesi Oluşturma
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6a1718e1f347be46b2f228479d3dbd30027b3160
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077440"
---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL Projesi Oluşturma

MFC DLL, birden çok uygulama tarafından aynı anda kullanılabilecek bir paylaşılan işlev kitaplığı olarak davranan bir ikili dosyadır. MFC DLL projesi oluşturmanın en kolay yolu MFC DLL Sihirbazı 'Nı kullanmaktır.

> [!NOTE]
>  IDE 'deki özelliklerin görünümü, etkin ayarlarınıza veya sürümüne bağlı olabilir ve yardım 'da açıklananlardan farklı olabilir. Ayarlarınızı değiştirmek için **Araçlar** menüsünden **Içeri ve dışarı aktarma ayarları** ' nı seçin. Daha fazla bilgi için bkz. [Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL Sihirbazı 'Nı kullanarak bir MFC DLL projesi oluşturmak için

1. [MFC uygulaması oluşturma](creating-an-mfc-application.md) yardım konusundaki yönergeleri izleyin, ancak kullanılabilir şablonlar listesinden **MFC dinamik bağlantı KITAPLıĞı** veya **MFC DLL** 'yi seçin.

1. [MFC DLL sihirbazının](../../mfc/reference/mfc-dll-wizard.md) [uygulama ayarları](../../mfc/reference/application-settings-mfc-dll-wizard.md) sayfasını kullanarak uygulama ayarlarınızı tanımlayın.

    > [!NOTE]
    >  Sihirbazın varsayılan ayarlarını korumak için bu adımı atlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın ve yeni projenizi **Çözüm Gezgini**açın.

Projeniz oluşturulduktan sonra, **Çözüm Gezgini**oluşturulan dosyaları görüntüleyebilirsiniz. Sihirbazın projeniz için oluşturduğu dosyalar hakkında daha fazla bilgi için, proje tarafından oluşturulan ReadMe. txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual Studio C++ projeleri Için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++Visual Studio 'da proje türleri](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)
