---
title: 'Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma'
ms.date: 05/06/2019
helpviewer_keywords:
- C++, creating projects from existing code
- Create New Project From Existing Code Files Wizard, project settings
f1_keywords:
- vc.appwiz.importwiz.location
- vc.appwiz.importwiz.appsettings
- vc.appwiz.importwiz.debugsettings
- vc.appwiz.importwiz.releasesettings
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
ms.openlocfilehash: 5e59230186380b787c95dbe08914bcd9d3ca2407
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078545"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma

Visual Studio 'da, varolan kod dosyalarından **Yeni proje oluştur** sihirbazını kullanarak C++ varolan kod dosyalarının bir projeye bağlantı noktası oluşturabilirsiniz. Bu sihirbaz, kaynak dosyalarını ve derleme yapılandırmasını yönetmek için MSBuild sistemini kullanan bir proje çözümü oluşturur. Karmaşık klasör hiyerarşileri olmayan görece basit projelerle en iyi şekilde işe yarar. Sihirbaz, Visual Studio 'nun daha eski Express sürümlerinde kullanılamaz.

Varolan kod dosyalarının bir C++ projeye AKTARıLMALARıNı, IDE içinde yerleşik olarak bulunan yerel MSBuild Proje Yönetimi özelliklerinin kullanılmasını sunar. Var olan derleme sisteminizi (NMAKE makefiles, CMake veya alternatifler gibi) kullanmayı tercih ediyorsanız, bunun yerine açık klasörü veya CMake seçeneklerini kullanabilirsiniz. Daha fazla bilgi için bkz. Visual Studio 'da [için C++ klasör projelerini açma](open-folder-projects-cpp.md) veya [CMake projeleri](cmake-projects-in-visual-studio.md). Her iki seçenek de [IntelliSense](/visualstudio/ide/using-intellisense) ve [Proje özellikleri](working-with-project-properties.md)gibi IDE özelliklerini kullanmanıza olanak sağlar.

### <a name="to-create-a-c-project-from-existing-code"></a>Varolan koddan bir C++ projesi oluşturmak için

1. **Dosya** menüsünde, **varolan koddan** **Yeni** > proje ' yi seçin.

1. Proje konumunuzu, kaynak dosyalarınızın dizinini ve sihirbazın yeni projeye aktardığı dosya türlerini belirtin. Devam etmek için **İleri ' yi** seçin.

    | Ayar | Açıklama |
    | --- | --- |
    | **Proje dosyası konumu** | Yeni projenin dizin yolunu belirtir. Bu konum, sihirbazın yeni projenin tüm dosyalarını (ve alt dizinlerini) mevdubudur.<br/><br/>**Proje dosyası konumu** iletişim kutusunu göstermek için **Araştır** ' ı seçin. Doğru klasöre gidin ve yeni projeyi içeren dizini belirtin. |
    | **Proje adı** | Yeni projenin adını belirtir. . Vcxproj gibi dosya uzantılarına sahip proje dosyaları, bu adı ve mevcut kod dosyalarını özgün adlarını tutar. |
    | **Bu klasörlerden dosyaları projeye Ekle** | Sihirbazı, mevcut kod dosyalarını özgün dizinlerinden (Bu denetimin altındaki liste kutusunda belirtilen) yeni projeye kopyalamak üzere ayarlamak için işaretleyin.<br/><br/>Tüm alt dizinlerden kod dosyalarını projeye kopyalamayı belirtmek için **alt klasör ekle** ' ye bakın. Dizinler **klasör** sütununda listelenir.<br/>-Sihirbazın var olan kod dosyalarını arayacağı dizinleri belirtmek için **Bu klasörden Proje Ekle iletişim kutusunda Dosya Ekle** ' **yi seçin.**<br/>-Liste kutusunda seçili dizin yolunu silmek için **Kaldır** ' ı seçin.<br/><br/>**Projeye eklenecek dosya türlerinde** , belirtilen dosya uzantılarına göre sihirbazın yeni projeye eklediği dosya türlerini belirtin. Dosya uzantıları önce yıldız işareti joker karakteriyle gelir ve dosya uzantıları listesinde noktalı virgülle ayrılır. |
    | **Tüm dosyaları Çözüm Gezgini göster** | Yeni projedeki tüm dosyaların **Çözüm Gezgini** penceresinde görünür ve görüntülenir olduğunu belirtir. Bu seçenek varsayılan olarak etkindir. |

    ![Proje konumu](media/location.png)

1. Yeni proje için yapı ortamı gibi kullanılacak proje ayarlarını ve oluşturulacak belirli bir yeni proje türüyle eşleşecek derleme ayarlarını belirtin. Devam etmek için **İleri ' yi** seçin.

    | Ayar | Açıklama |
    | --- | --- |
    | **Visual Studio kullanma** | Yeni projeyi oluşturmak için Visual Studio 'ya dahil edilen derleme araçlarının kullanılacağını belirtir. Bu seçenek varsayılan olarak seçilidir.<br/><br/>Sihirbazın oluşturduğu proje türünü belirtmek için **proje türünü** seçin. **Windows uygulama projesi**, **konsol uygulama projesi**, **dınamık olarak bağlı kitaplık (dll) PROJESI**veya **statik kitaplık (LIB) projesi**seçin.<br/><br/>Yeni projeye ATL desteği eklemek için **atl desteği ekle** ' ye bakın.<br/><br/>Yeni projeye MFC desteği eklemek için **MFC desteği ekleyin** ' i işaretleyin.<br/><br/>Projeye CLR programlama desteği eklemek için **ortak dil çalışma zamanı desteği ekleyin** ' i işaretleyin. Sözdizimi için C++ yönetilen uzantılar ile uyumluluk için ortak dil çalışma zamanı **(eski sözdizimi)** , Visual Studio 2005 ' den önceki CLR programlama sözdizimi gibi uyumluluk türü Için **ortak dil çalışma zamanı desteğini** seçin. |
    | **Dış yapı sistemi kullan** | Yeni projeyi oluşturmak için Visual Studio 'ya dahil olmayan yapı araçlarının kullanılacağını belirtir. Bu seçenek belirlendiğinde, **hata ayıklama yapılandırma ayarlarını belirtin** ve **Yayın yapılandırma ayarlarını belirtin** sayfasında derleme komut satırları ' nı belirtebilirsiniz. |

    ![Proje ayarları](media/settings.png)

    > [!NOTE]
    > **Dış yapı sistemi kullan** seçeneği IŞARETLENDIĞINDE, IDE projeyi oluşturmaz, bu nedenle/D,/I,/FI,/AI veya/Fu seçenekleri derleme için gerekli değildir. Ancak, IntelliSense 'in düzgün çalışması için bu seçeneklerin doğru şekilde ayarlanması gerekir.

1. Kullanılacak hata ayıklama yapılandırma ayarlarını belirtin. Devam etmek için **İleri ' yi** seçin.

    | Ayar | Açıklama |
    | --- | --- |
    | **Derleme komut satırı** | Projeyi oluşturan komut satırını belirtir. Derleyicinin adını (artı herhangi bir anahtar veya bağımsız değişken) ya da projeyi derlemek için kullanmak istediğiniz derleme betikleri girin. |
    | **Komut satırını yeniden oluştur** | Yeni projeyi yeniden oluşturan komut satırını belirtir. |
    | **Temizle komut satırı** | Proje için yapı araçları tarafından oluşturulan destek dosyalarını silmek için komut satırını belirtir. |
    | **Çıkış (hata ayıklama için)** | Projenin hata ayıklama yapılandırması için çıkış dosyalarının dizin yolunu belirtir. |
    | **Önişlemci tanımları (/D)** | Proje için önişlemci sembolleri tanımlar, bkz. [/d (Önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md). |
    | **Arama yolunu ekle (/I)** | Derleyicinin, projedeki Önişlemci yönergelerine geçilen dosya başvurularını çözümlemek için arayacağı dizin yollarını belirtir, bkz. [/i (ek Içerme dizinleri)](../build/reference/i-additional-include-directories.md). |
    | **Zorunlu eklenen dosyalar (/FI)** | Projeyi oluştururken işlenecek üst bilgi dosyalarını belirtir, bkz. [/Fi (zorunlu Içerme dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md). |
    | **.NET bütünleştirilmiş kod arama yolu (/AI)** | Derleyicinin, projedeki Önişlemci yönergelerine geçirilen .NET derleme başvurularını çözümlemek için arayacağı dizin yollarını belirtir, bkz. [/AI (meta veri dizinlerini belirt)](../build/reference/ai-specify-metadata-directories.md). |
    | **.NET derlemeleri (/FU) kullanılarak zorlandı** | Projeyi oluştururken işlenecek .NET derlemelerini belirtir, bkz. [/Fu (zorlanan #using dosyayı adlandır)](../build/reference/fu-name-forced-hash-using-file.md). |

    ![Proje yapılandırması](media/config.png)

    > [!NOTE]
    > **Derleme**, **yeniden oluşturma**, **Temizleme** komut satırı ve **Çıkış (hata ayıklama için)** ayarları yalnızca **Proje ayarlarını belirtin** sayfasında **dış yapı sistemi kullan** seçeneği işaretliyse etkinleştirilir.

1. Kullanılacak yayın yapılandırma ayarlarını belirtin, bu ayarlar hata ayıklama yapılandırma ayarları ile aynıdır. Yeni projeyi oluşturmak için **son** ' a tıklayın.

    > [!NOTE]
    > Burada, sihirbazın yapılandırma projesi ayarlarında hata ayıklama ile aynı sürüm yapılandırma proje ayarlarını oluşturmasını belirtmek için **hata ayıklama yapılandırmasıyla aynı şekilde** bakabilirsiniz. Bu seçenek varsayılan olarak işaretlidir. Bu kutunun işaretini kaldırmanız gerekmedikçe, bu sayfadaki diğer tüm seçenekler etkin değildir.
