---
title: Visual Studio'da C++ derleme görevleri dosyası projesi oluşturma
ms.date: 12/08/2018
f1_keywords:
- vc.appwiz.makefile.project
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
ms.openlocfilehash: 9c2edfe35233672e8117d336ba40cfea497b1a22
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272353"
---
# <a name="create-a-c-makefile-project"></a>C++ derleme görevleri dosyası projesi oluşturma

A *derleme görevleri dosyası* derleme ve bağlama ilişkin yönergeleri içeren bir metin dosyasıdır (veya *derleme*) C++ kaynak kodu dosyaları kümesi. A *olun* program derleme görevleri dosyası okur ve bir derleyici, bağlayıcı ve büyük olasılıkla diğer programları yürütülebilir bir dosya olmak için çağırır. Microsoft'un *olun* program çağrılır [NMAKE](nmake-reference.md);

Mevcut bir derleme görevleri dosyası projesi varsa, kod ve/veya Visual Studio IDE içinde hata ayıklamak istiyorsanız bu seçeneğiniz vardır:

- Visual Studio'da Visual Studio IntelliSense için kullanacağı bir .vcxproj dosyası yapılandırmak için mevcut derleme görevleri dosyası kullanan bir derleme görevleri dosyası projesi oluşturun. (, Yerel bir MSBuild projesi ile aldığınız tüm IDE özelliklerini yoktur.) Bkz: [makefile projesi oluşturmak için](#create_a_makefile_project) aşağıda.
- Kullanım **varolan kod dosyalarından yeni proje oluştur** kaynak kodunuzu yerel bir MSBuild projesi oluşturmak için Sihirbazı. Orijinal derleme görevleri dosyası bundan sonra kullanılmaz. Daha fazla bilgi için [nasıl yapılır: Varolan koddan C++ projesi oluşturma](../how-to-create-a-cpp-project-from-existing-code.md).
- **Visual Studio 2017 ve üzeri**: Kullanım **Klasör Aç** düzenleyin ve bir derleme görevleri dosyası projesi olarak oluşturmak için özellik-tüm MSBuild sistemi katılımı olduğu. Daha fazla bilgi için [C++ açık klasörü projelerde](../open-folder-projects-cpp.md).

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> Derleme görevleri dosyası proje şablonuyla bir derleme görevleri dosyası projesi oluşturmak için

Visual Studio 2017 ve sonraki sürümlerinde, C++ masaüstü geliştirme iş yükü yüklendiğinde Makefile projesi şablonunu kullanılabilir.

Komutlar ve ortam, derleme görevleri dosyası tarafından kullanılan belirtmek için sihirbazı izleyin. Ardından bu projeyi Visual Studio'da, kodunuzu derlemek için de kullanabilirsiniz.

Varsayılan olarak, derleme görevleri dosyası projesi hiçbir dosya Çözüm Gezgini'nde görüntüler. Derleme görevleri dosyası proje, projenin özellik sayfasına yansıyan derleme ayarlarını belirtir.

Projede belirttiğiniz çıktı dosyasının, derleme komut dosyasının oluşturduğu ad üzerinde hiçbir etkisi yoktur; yalnızca bir amaç belirtir. Derleme görevleri dosyası yine de derleme işlemini denetler ve yapı hedeflerini belirtir.

1. "Derleme görevleri dosyası" yazın Visual Studio başlangıç sayfasından **yeni proje** arama kutusu. Veya **yeni proje** iletişim kutusunda **Visual C++** > **genel** (Visual Studio 2015) veya **diğer** (görsel Studio 2017'de) ve ardından **derleme görevleri dosyası projesi** Proje Sihirbazı'nı açmak için şablonlar bölmesindeki.

1. İçinde **uygulama ayarları** sayfasında, komut çıktısında, temizleme ve yeniden oluşturma bilgileri için hata ayıklama ve perakende derlemeleri sağlayın.

1. Tıklayın **son** sihirbazı kapatın ve yeni oluşturulan projeyi **Çözüm Gezgini**.

Özellik sayfasında projenin özelliklerini görüntüleyebilir ve düzenleyebilirsiniz. Bkz: [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md) özellik sayfasını görüntüleme hakkında bilgi.

## <a name="makefile-project-wizard"></a>Derleme görevleri dosyası projesi Sihirbazı

Bir derleme görevleri dosyası projesi oluşturduktan sonra görüntüleyebilir ve her biri aşağıdaki seçenekleri Düzenle **Nmake** sayfası proje özellik sayfası.

- **Komut satırı derleme:** Kullanıcı yapı derle menüsünde seçtiğinde çalıştırılacak komut satırını belirtir. Nmake sayfasında projenin özellik sayfasının derleme komut satırı alanında görüntülenir.

- **Çıkış:** Çıkış komut satırı içerecek dosyanın adını belirtir. Varsayılan olarak, bu seçenek, proje adını temel alır. Nmake sayfasında projenin özellik sayfasının çıkış alanında görüntülenir.

- **Temiz komutlar:** Kullanıcı derle menüsünde temiz seçtiğinde çalıştırılacak komut satırını belirtir. Nmake sayfasında projenin özellik sayfasının temiz komut satırı alanında görüntülenir.

- **Yeniden derle komut satırı:** Kullanıcı yeniden derle menüsünde seçtiğinde çalıştırılacak komut satırını belirtir. Yeniden tüm komut satırı alanı projenin özellik sayfası Nmake sayfasında görüntülenir.

## <a name="how-to-enable-intellisense-for-makefile-projects"></a>Nasıl yapılır: Derleme görevleri dosyası projeleri için IntelliSense'i etkinleştirme

Belirli proje ayarları veya derleyici seçenekleri hatalı ayarlandığında IntelliSense içinde derleme görevleri dosyası projeleri başarısız olur. Derleme görevleri dosyası projeleri IntelliSense beklendiği gibi çalıştığını şekilde yapılandırmak için şu adımları izleyin:

1. Açık **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Seçin **NMake** özellik sayfa ve Özellikler altında değiştirin **IntelliSense** uygun şekilde.

   - Ayarlama **önişlemci tanımları** derleme görevleri dosyası projenize önişlemci simgeleri tanımlamak için özellik. Bkz: [/D (önişlemci tanımları)](d-preprocessor-definitions.md), daha fazla bilgi için.

   - Ayarlama **arama yolu Ekle** özelliği, derleme görevleri dosyası projesi ön işlemci yönergelerinde geçirilen dosya başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri listesini belirtin. Bkz: [/ı (ek içeren dizinler)](i-additional-include-directories.md), daha fazla bilgi için.

    - CL kullanılarak oluşturulan projeler için. Komut penceresinden EXE ayarlamak **INCLUDE** önişlemci yönergeleri, derleme görevleri dosyası projesi içinde geçirilen dosya başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri belirlemenize imkan ortam değişkeni.

   - Ayarlama **zorunlu içerir** özelliği, derleme görevleri dosyası projesi oluşturma sırasında hangi başlığı işlenecek dosyaları belirtmek için. Bkz: [/FI (zorla dahil dosyasını Adlandır)](fi-name-forced-include-file.md), daha fazla bilgi için.

   - Ayarlama **bütünleştirilmiş kod arama yolu** özelliği, projenizdeki .NET derlemelerin başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri listesini belirtin. Bkz: [/AI (meta veri dizinlerini belirtin)](ai-specify-metadata-directories.md), daha fazla bilgi için.

   - Ayarlama **kullanarak derlemeleri zorunlu** özelliği, derleme görevleri dosyası projesi oluşturma sırasında işlenecek hangi .NET derlemelerini belirtin. Bkz: [/FU (zorlanan adı #using)](fu-name-forced-hash-using-file.md), daha fazla bilgi için.

   - Ayarlama **ek seçenekler** özelliği C++ dosyaları ayrıştırılırken IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtin.

1. Tıklayın **Tamam** özellik sayfalarını kapatmak için.

1. Kullanım **Tümünü Kaydet** değiştirilen proje ayarları kaydetmek için komutu.

Sonraki açışınızda, derleme görevleri dosyası projesi çalıştırma Visual Studio geliştirme ortamında **çözümü Temizle** komutunu ve ardından **Çözümü Derle** derleme görevleri dosyası projenize komutu. IntelliSense, IDE'de düzgün çalışması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[IntelliSense Kullanma](/visualstudio/ide/using-intellisense)<br>
[NMAKE Başvurusu](nmake-reference.md)<br>
[Nasıl yapılır: Varolan koddan C++ projesi oluşturma](../how-to-create-a-cpp-project-from-existing-code.md)
[derleme görevleri dosyasındaki özel karakterler](special-characters-in-a-makefile.md)<br/>
[Derleme Görevleri Dosyası İçeriği](contents-of-a-makefile.md)<br/>
