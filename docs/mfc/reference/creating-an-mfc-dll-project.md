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
ms.openlocfilehash: 6367b2a4b85b2c586c5a4420a8be1f80d334b2e4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363955"
---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL Projesi Oluşturma

MFC DLL, birden çok uygulama tarafından aynı anda kullanılabilen işlevlerin paylaşılan kitaplığı gibi davranan ikili bir dosyadır. Bir MFC DLL projesi oluşturmanın en kolay yolu MFC DLL Sihirbazı'nı kullanmaktır.

> [!NOTE]
> IDE'deki özelliklerin görünümü etkin ayarlarınıza veya sürümünüze bağlı olabilir ve Yardım'da açıklananlardan farklı olabilir. Ayarlarınızı değiştirmek için **Araçlar** menüsünde **Ayarlar İçe Ve Dışa Aktar'ı** seçin. Daha fazla bilgi için [Visual Studio IDE'yi Kişiselleştir'e](/visualstudio/ide/personalizing-the-visual-studio-ide)bakın.

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL Sihirbazı'nı kullanarak bir MFC DLL Projesi oluşturmak için

1. [Yardım konusuMFC Uygulaması oluşturma](creating-an-mfc-application.md) yönergelerini izleyin, ancak kullanılabilir şablonlar listesinden **MFC Dinamik Bağlantı Kitaplığı'nı** veya **MFC DLL'yi** seçin.

1. [MFC DLL Sihirbazı'nın](../../mfc/reference/mfc-dll-wizard.md) [uygulama ayarları](../../mfc/reference/application-settings-mfc-dll-wizard.md) sayfasını kullanarak uygulama ayarlarınızı tanımlayın.

    > [!NOTE]
    >  Sihirbaz varsayılan ayarlarını tutmak için bu adımı atlayın.

1. Sihirbazı kapatmak ve **Çözüm Gezgini'nde**yeni projenizi açmak için **Bitir'i** tıklatın.

Projeniz oluşturulduktan **sonra, Solution Explorer'da**oluşturulan dosyaları görüntüleyebilirsiniz. Sihirbazın projeniz için oluşturduğu dosyalar hakkında daha fazla bilgi için proje tarafından oluşturulan ReadMe.txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için [Visual Studio C++ projeleri için Oluşturulan Dosya Türleri'ne](../../build/reference/file-types-created-for-visual-cpp-projects.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C++ proje türleri](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)
