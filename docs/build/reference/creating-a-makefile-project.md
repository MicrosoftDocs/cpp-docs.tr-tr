---
title: Visual Studio 'da C++ Makefile projesi oluşturma
ms.date: 08/05/2019
f1_keywords:
- vc.appwiz.makefile.project
helpviewer_keywords:
- Makefile projects [C++]
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
ms.openlocfilehash: 69e6a2ff0d7e82f3bc431a28f57127e8d9a3aa4d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921535"
---
# <a name="create-a-c-makefile-project"></a>C++ Makefile projesi oluşturma

*Derleme görevleri* dosyası, C++ kaynak kodu dosyalarını derleyip bağlama (veya *derleme* ) ile ilgili yönergeler içeren bir metin dosyasıdır. Bir *Make* programı, derleme görevleri dosyasını okur ve bir derleyici, bağlayıcı ve büyük olasılıkla diğer programları bir yürütülebilir dosya yapmak için çağırır. Microsoft 'un *Make* programı uygulamasına [NMAKE](nmake-reference.md)adı verilir.

Mevcut bir derleme görevleri dosyası projeniz varsa, Visual Studio IDE 'de kod ve/veya hata ayıklama yapmak istiyorsanız, bu seçeneklere sahip olursunuz:

- Visual Studio 'da, Visual Studio 'nun IntelliSense için kullanacağı bir. vcxproj dosyasını yapılandırmak için mevcut derleme görevleri dosyasını kullanan bir derleme görevleri dosyası projesi oluşturun. (Yerel bir MSBuild projesiyle aldığınız tüm IDE özelliklerine sahip değilsiniz.) Aşağıdaki [bir derleme görevleri dosyası projesi oluşturmak için](#create_a_makefile_project) bölümüne bakın.
- Kaynak kodunuzda yerel bir MSBuild projesi oluşturmak için **varolan kod dosyalarından yeni proje oluşturma** Sihirbazı 'nı kullanın. Özgün derleme görevleri dosyası bundan sonra kullanılmaz. Daha fazla bilgi için bkz. [nasıl yapılır: Varolan koddan C++ projesi oluşturma](../how-to-create-a-cpp-project-from-existing-code.md).
- **Visual Studio 2017 ve üzeri** : MSBuild sisteminin herhangi bir katılımı olmadan bir derleme görevleri dosyası projesini düzenlemek ve oluşturmak Için **klasörü aç** özelliğini kullanın. Daha fazla bilgi için bkz. [C++ Için klasör projelerini açma](../open-folder-projects-cpp.md).
- **Visual Studio 2019 ve üzeri** : LINUX için UNIX makefile projesi oluşturun.

## <a name="a-namecreate_a_makefile_project-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> Derleme görevleri dosyası projesi şablonu ile bir Makefile projesi oluşturmak için

Visual Studio 2017 ve üzeri sürümlerde, derleme görevleri dosyası proje şablonu, C++ masaüstü geliştirme iş yükü yüklenirken kullanılabilir.

Derleme görevleri dosyası tarafından kullanılan komutları ve ortamı belirtmek için Sihirbazı izleyin. Daha sonra bu projeyi, Visual Studio 'da kodunuzu oluşturmak için kullanabilirsiniz.

Varsayılan olarak, makefile projesi Çözüm Gezgini dosya görüntülemez. Derleme görevleri dosyası projesi, projenin özellik sayfasına yansıtılan derleme ayarlarını belirtir.

Projede belirttiğiniz çıktı dosyasının, derleme komut dosyasının oluşturduğu ad üzerinde hiçbir etkisi yoktur; yalnızca bir amaç belirtir. Derleme görevleri dosyası derleme işlemini hala denetler ve derleme hedeflerini belirler.

::: moniker range="msvc-160"

### <a name="to-create-a-makefile-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir Makefile projesi oluşturmak için

1. Visual Studio ana menüsünde **Dosya**  >  **Yeni**  >  **Proje** ' yi seçin ve arama kutusuna "Makefile" yazın. Ya da **Yeni proje** iletişim kutusunda **Visual C++**  >  **General** (Visual Studio 2015) veya **Other** (Visual Studio 2017) öğesini genişletin ve ardından Windows veya Linux 'un hedeflemesine bağlı olarak iki seçenekten istediğinizi seçin.

1. **Yalnızca Windows** : **hata ayıklama yapılandırma ayarları** sayfasında hata ayıklama ve perakende Derlemeleriyle ilgili komut, çıkış, temizleme ve yeniden oluşturma bilgilerini sağlayın. Bir yayın yapılandırması için farklı ayarlar belirtmek istiyorsanız **İleri** ' ye tıklayın.

1. İletişim kutusunu kapatmak ve **Çözüm Gezgini** yeni oluşturulan projeyi açmak için **son** ' a tıklayın.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-a-makefile-project-in-visual-studio-2015-or-visual-studio-2017"></a>Visual Studio 2015 veya Visual Studio 2017 ' de bir Makefile projesi oluşturmak için

1. Visual Studio başlangıç sayfasından **Yeni proje** arama kutusuna "Makefile" yazın. Ya da **Yeni proje** iletişim kutusunda, **Visual C++**  >  **General** (Visual Studio 2015) veya **Other** (Visual Studio 2017) öğesini genişletin ve ardından Proje Sihirbazı 'nı açmak için Şablonlar bölmesinde **makefile projesi** öğesini seçin.

1. **Uygulama ayarları** sayfasında hata ayıklama ve perakende Derlemeleriyle ilgili komut, çıkış, temizleme ve yeniden oluşturma bilgilerini sağlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın ve yeni oluşturulan projeyi **Çözüm Gezgini** açın.

::: moniker-end

Özellik sayfasında projenin özelliklerini görüntüleyebilir ve düzenleyebilirsiniz. Özellik sayfasını görüntüleme hakkında bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md) .

## <a name="makefile-project-wizard"></a>Derleme görevleri dosyası proje Sihirbazı

Derleme görevleri dosyası projesi oluşturduktan sonra, projenin özellik sayfasının **NMAKE** sayfasında aşağıdaki seçeneklerden her birini görüntüleyebilir ve düzenleyebilirsiniz.

- **Derleme komut satırı:** Kullanıcı Build menüsünden Build ' i seçtiğinde çalıştırılacak komut satırını belirtir. Projenin Özellik sayfasının NMAKE sayfasında yer alan derleme komut satırı alanında gösterilir.

- **Çıkış:** Komut satırı için çıktıyı içerecek dosyanın adını belirtir. Varsayılan olarak, bu seçenek proje adına dayalıdır. Projenin Özellik sayfasının NMAKE sayfasında çıktı alanında gösterilir.

- **Temizleme komutları:** Kullanıcı derleme menüsünden temiz seçtiğinde çalıştırılacak komut satırını belirtir. Projenin Özellik sayfasının NMAKE sayfasında bulunan komut satırını temizle alanında gösterilir.

- **Komut satırını yeniden oluştur:** Kullanıcı derleme menüsünden yeniden oluştur seçildiğinde çalıştırılacak komut satırını belirtir. Projenin Özellik sayfasının NMAKE sayfasında tüm komut satırını yeniden oluştur alanında gösterilir.

## <a name="how-to-enable-intellisense-for-makefile-projects"></a>Nasıl Yapılır: Derleme Görevleri Dosyası Projeleri için IntelliSense'i Etkinleştirme

Belirli proje ayarları veya derleyici seçenekleri hatalı ayarlandığında IntelliSense, derleme görevleri dosyası projelerinde başarısız olur. IntelliSense 'in beklendiği gibi çalışması için derleme görevleri dosyası projelerini yapılandırmak için aşağıdaki adımları izleyin:

1. **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **NMAKE** özellik sayfasını seçin ve ardından **IntelliSense** altındaki özellikleri uygun şekilde değiştirin.

   - **Önişlemci tanımları** özelliğini, derleme görevleri dosyası projenizdeki herhangi bir Önişlemci sembolü tanımlamak için ayarlayın. Daha fazla bilgi için bkz. [/d (Önişlemci tanımları)](d-preprocessor-definitions.md).

   - Derleme görevleri dosyası projenizdeki Önişlemci yönergelerine geçirilen dosya başvurularını çözümlemek üzere arama yapılacak dizinlerin listesini belirtmek için **arama yolunu dahil etme** özelliğini ayarlayın. Daha fazla bilgi için bkz. [/i (ek ekleme dizinleri)](i-additional-include-directories.md).

   - Komut penceresinden CL.EXE kullanılarak oluşturulan projeler için, **Include** ortam değişkenini, derleyicinin derleme görevleri dosyası projenizdeki Önişlemci yönergelerine geçirilen dosya başvurularını çözümlemek üzere arayacağını belirlemek için ayarlayın.

   - Derleme görevleri dosyası projenizi oluştururken hangi başlık dosyalarının işlemesini belirtmek için **zorunlu içerme** özelliğini ayarlayın. Daha fazla bilgi için bkz. [/Fi (zorunlu Içerme dosyasını adlandırma)](fi-name-forced-include-file.md).

   - Derleyicinin, projenizdeki .NET derlemelerine başvuruları çözümlemek üzere arayacağını belirten dizinlerin listesini belirtmek için **Derleme arama yolu** özelliğini ayarlayın. Daha fazla bilgi için bkz. [/AI (meta veri dizinlerini belirt)](ai-specify-metadata-directories.md).

   - Derleme görevleri dosyası projenizi oluştururken hangi .NET derlemelerinin işlemesini belirtmek için **zorlamalı using derlemeler** özelliğini ayarlayın. Daha fazla bilgi için bkz. [/Fu (zorlanan #using dosyasına ad)](fu-name-forced-hash-using-file.md).

   - C++ dosyalarını ayrıştırırken IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtmek için **ek seçenekler** özelliğini ayarlayın.

1. Özellik sayfalarını kapatmak için **Tamam** ' ı tıklatın.

1. Değiştirilen proje ayarlarını kaydetmek için **Tümünü Kaydet** komutunu kullanın.

Visual Studio geliştirme ortamında derleme görevleri dosyası projenizi bir sonraki açışınızda, **Clean Solution** komutunu ve sonra derleme görevleri dosyası projenizden **Build Solution** komutunu çalıştırın. IntelliSense IDE 'de düzgün çalışmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[IntelliSense kullanma](/visualstudio/ide/using-intellisense)<br>
[NMAKE Başvurusu](nmake-reference.md)<br>
[Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../how-to-create-a-cpp-project-from-existing-code.md)<br>
[Derleme görevleri dosyasındaki özel karakterler](special-characters-in-a-makefile.md)<br/>
[Derleme görevleri dosyası içeriği](contents-of-a-makefile.md)<br/>
