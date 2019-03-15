---
title: Visual Studio projeleri - C++
ms.date: 12/12/2018
f1_keywords:
- vcprojects
- creatingmanagingVC
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
ms.openlocfilehash: b5fb9ac87547578f101676d4cf424c7065155842
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823659"
---
# <a name="visual-studio-projects---c"></a>Visual Studio projeleri - C++

A *Visual Studio projesi* proje MSBuild yapı sistemini temel alır. MSBuild Visual Studio için yerel derleme sistemi ve genellikle en iyi MFC veya ATL kitaplığı, COM bileşenleri ve diğer Windows özel programları kullanan masaüstü uygulamaların yanı sıra UWP uygulamaları için kullanılacak sistem oluşturun. MSBuild Visual Studio ile tümleşiktir, ancak bunu ayrıca komut satırından kullanabilirsiniz. 

## <a name="create-a-project"></a>Proje oluşturma

C++ projeleri seçerek oluşturabilirsiniz **dosya &#124; yeni &#124; proje**, Visual C++'ın sol bölmesinde seçerek sonra. Orta bölmede, proje şablonları listesi görürsünüz: 

   ![Proje şablonları](../media/vs2017-new-project.png "Visual Studio 2017 yeni proje iletişim kutusu")

Visual Studio'ya dahil olan tüm varsayılan proje şablonları hakkında daha fazla bilgi için bkz: [Visual Studio'da C++ proje şablonları](reference/visual-cpp-project-types.md). Kendi proje şablonları oluşturabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Proje şablonları oluşturma](/visualstudio/ide/how-to-create-project-templates).

Bir proje oluşturduğunuzda görünür [Çözüm Gezgini](/visualstudio/ide/solutions-and-projects-in-visual-studio) penceresi:

   ![Çözüm Gezgini](media/mathlibrary-solution-explorer-153.png)

Yeni bir proje oluşturduğunuzda, çözüm dosyasına (.sln) da oluşturulur. İçinde sağ tıklayarak ek projeleri çözüme ekleyebilirsiniz **Çözüm Gezgini**. Çözüm dosyası, birden çok ilgili proje sahip ancak daha çok daha fazlasını yapın değil derleme bağımlılıkları koordine etmek için kullanılır. Tüm derleyici seçenekleri, proje düzeyinde ayarlanır.

## <a name="add-items"></a>Öğeleri Ekle

Ekleme kaynak kodu dosyaları, simgeler ve diğer öğeleri projenize projeye sağ tıklayarak **Çözüm Gezgini** seçip **Ekle > Yeni** veya **Ekle > varolan**.

## <a name="add-third-party-libraries"></a>Üçüncü taraf kitaplıklar ekleme

Üçüncü taraf kitaplıklarını eklemek için [vcpkg](../vcpkg.md) Paket Yöneticisi. Tüm Visual Studio projesinden başvuru yaptığınızda bu kitaplık yollarını ayarlamak için Visual Studio Tümleştirme adımını çalıştırın. 

## <a name="set-compiler-options-and-other-build-properties"></a>Derleyici seçeneklerini ayarlama ve diğer derleme özellikleri

Proje derleme ayarlarını yapılandırmak için projeyi sağ tıklatın **Çözüm Gezgini** ve **özellikleri**. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](working-with-project-properties.md).

## <a name="compile-and-run"></a>Derleme ve çalıştırma

Yeni Projeyi derlemek ve çalıştırmak için basın **F5** veya *açılan hata ayıklama* ana araç çubuğundaki yeşil bir ok. *Yapılandırma açılan* nerede yapılıp yapılmayacağını seçin bir *hata ayıklama* veya *yayın* derleme (veya başka bir özel yapılandırma).

Yeni bir proje hata olmadan derler. Kendi kodunuzu eklerken, bazen bir hata oluşturur veya bir uyarı tetikler. Bir hata, yapı işleminin tamamlanmasını engelliyor; bir uyarı vermez. Proje oluşturduğunuzda tüm hataları ve Uyarıları hem çıktı penceresinde hem de hata listesinde görünür. 

   ![Çıkış penceresi ve hata listesi](../media/vs2017-output-error-list.png)

Hata listesinde basabilirsiniz **F1** vurgulanan hatada kendi belgeleri konusuna gidin.

## <a name="in-this-section"></a>Bu Bölümde

[C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri](working-with-project-properties.md)<br/>
Proje ayarlarınızı belirtmek için özellik sayfaları ve özellik sayfalarını kullanma

[Başvuru kitaplıkları ve derleme zamanında bileşenleri](adding-references-in-visual-cpp-projects.md)<br/>
Nasıl bir projede kitaplıklar, DLL'ler COM ve .NET bileşenleri içerir.
 
[Proje çıktı dosyalarını düzenleme](how-to-organize-project-output-files-for-builds.md)<br/>
Yapı işlemi sırasında oluşturulan yürütülebilir dosyalarının konumunu özelleştirmek nasıl.

[Özel derleme adımlarını ve derleme olaylarını](understanding-custom-build-steps-and-build-events.md)<br/>
Derleme işlemi sırasında isteğe bağlı bir komut ekleme noktası belirtilmemiş.

[Mevcut koddan proje oluşturma](how-to-create-a-cpp-project-from-existing-code.md)<br/>
Kaynak dosyaları gevşek koleksiyonundan yeni bir Visual Studio projesi oluşturma

## <a name="see-also"></a>Ayrıca Bkz.

[Projeler ve yapı sistemi](projects-and-build-systems-cpp.md)<br>
