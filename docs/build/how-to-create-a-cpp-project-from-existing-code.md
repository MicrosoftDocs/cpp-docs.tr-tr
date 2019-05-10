---
title: 'Nasıl yapılır: Varolan koddan C++ projesi oluşturma'
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
ms.openlocfilehash: a899fe7f1b038ac1497465171098183f63f40564
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221461"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Nasıl yapılır: Varolan koddan C++ projesi oluşturma

Visual Studio'da, varolan kod dosyaları kullanarak bir C++ projesi bağlantı noktası **oluşturma yeni proje varolan kod dosyalarından** Sihirbazı. Bu sihirbaz, kaynak dosyaları yönetmek ve derleme yapılandırması için MSBuild sistemini kullanan bir proje çözüm oluşturur. En iyi, karmaşık bir klasör hiyerarşisi yoktur görece basit projeleriyle çalışır. Sihirbaz, Visual Studio'nun eski Express sürümlerinde kullanılamaz. 

Varolan kod dosyaları bir C++ projesine taşımak, IDE içine yerleşik yerel MSBuild proje yönetimi özellikleri sağlar. Nmake derleme görevleri dosyalarını, CMake veya alternatifleri gibi var olan, derleme sisteminizi kullanmayı tercih ederseniz, bunun yerine açık klasör veya CMake seçeneklerini kullanabilirsiniz. Daha fazla bilgi için [C++ açık klasörü projelerde](open-folder-projects-cpp.md) veya [Visual Studio'daki CMake projeleri](cmake-projects-in-visual-studio.md). İki seçenek de gibi IDE özelliklerini kullanmanıza izin [IntelliSense](/visualstudio/ide/using-intellisense) ve [proje özellikleri](working-with-project-properties.md).

### <a name="to-create-a-c-project-from-existing-code"></a>Varolan koddan bir C++ projesi oluşturmak için

1. Üzerinde **dosya** menüsünde **yeni** > **varolan koddan proje**.

1. Proje konumu, kaynak dosyalarınızı ve dosyaları yeni projeye sihirbaz aktarır türleri için dizini belirtin. Seçin **sonraki** devam etmek için.

    | Ayar | Açıklama |
    | --- | --- |
    | **Proje dosya konumu** | Yeni Proje dizini yolunu belirtir. Sihirbaz tüm dosyaları (ve alt dizinleri) yeni projenin nerede elverdiği bu konumdur.<br/><br/>Seçin **Gözat** görüntülenecek **proje dosya konumu** iletişim. Doğru klasöre gidin ve yeni projeyi içeren dizini belirtin. |
    | **Proje adı** | Yeni proje adını belirtir. Proje dosyaları, bu ad .vcxproj devralır ve kendi özgün adı varolan kod dosyaları tutmak gibi dosya uzantılarına sahiptir. |
    | **Dosyalar projeye bu klasörlerden ekleyin.** | Varolan kod dosyaları (Bu, liste kutusunda Bu denetimin altında belirtilir), özgün dizin kopyalamak için Sihirbazı ayarlanacak yeni projeye denetleyin.<br/><br/>Denetleme **alt klasörleri Ekle** projeye tüm alt dizinleri kopyalama kod dosyalarından belirtmek için. Dizinleri listelenen **klasör** sütun.<br/>-Select **Ekle** görüntülenecek **ekleme dosyaları projeye bu klasörden** iletişim kutusu, sihirbaz varolan kod dosyaları arar dizinleri belirtmek için.<br/>-Select **Kaldır** liste kutusunda seçili dizin yolu silinemedi.<br/><br/>İçinde **dosya projeye eklenecek türleri** kutusunda, Sihirbazı belirli dosya uzantılarını temel alan yeni proje ekler. dosya türü belirtin. Dosya uzantıları, yıldız işareti joker karakteriyle öncesinde ve noktalı virgülle ayrılmış dosya uzantıları listesinde. |
    | **Çözüm Gezgini içindeki tüm dosyaları göster** | Tüm dosyaları görünür ve görüntülenen yeni projede belirtir **Çözüm Gezgini** penceresi. Bu seçenek varsayılan olarak etkindir. |

    ![Proje konumu](media/location.png)

1. Yeni proje için yapı ortamı gibi kullanmak için proje ayarları ve oluşturulacak yeni projenin belirli bir türüyle eşleşecek şekilde derleme ayarlarını belirtin. Seçin **sonraki** devam etmek için.

    | Ayar | Açıklama |
    | --- | --- |
    | **Visual Studio'yu kullanın.** | Visual Studio'da yeni proje oluşturmak için dahil edilen derleme araçları kullanılacağını belirtir. Bu seçenek varsayılan olarak seçilidir.<br/><br/>Seçin **proje türü** Sihirbazı'nın ürettiği projenin türünü belirtmek için. Seçin **Windows uygulaması projesi**, **konsol uygulama projesi**, **dinamik olarak bağlı bir kitaplığı (DLL) projesi**, veya **statik kitaplık (LIB) Proje**.<br/><br/>Denetleme **ATL için destek ekleme** yeni projeye ATL desteği eklenecek.<br/><br/>Denetleme **MFC desteği ekleme** yeni proje için MFC desteği eklemek için.<br/><br/>Denetleyin **ortak dil çalışma zamanı için destek ekleme** CLR programlama desteği projeye eklenecek. Seçin **ortak dil çalışma zamanı desteği** uyumluluk türü gibi **ortak dil çalışma zamanı (eski sözdizimi)** için Yönetilen Uzantılar'ile uyumluluğu C++ söz dizimi, CLR programlama sözdizimi Visual Studio 2005'den önce. |
    | **Dış yapı ortamı kullanın** | Visual Studio'da yeni proje oluşturmak için yer almayan derleme araçları kullanılacağını belirtir. Bu seçenek belirlendiğinde, derleme komut satırları belirtebilirsiniz **hata ayıklama yapılandırma ayarlarını belirt** ve **sürüm yapılandırma ayarlarını belirt** sayfaları. |

    ![Proje ayarları](media/settings.png)

    > [!NOTE]
    > Zaman **kullanım dış yapı sistemi** seçeneği, IDE Proje yapı değil böylece /D, / ı, /FI, /AI veya /FU seçenekleri derleme için gerekli değildir. Ancak, bu seçenekler sırada düzgün çalışması IntelliSense doğru şekilde ayarlanmalıdır.

1. Hata ayıklama yapılandırma ayarlarını belirtin. Seçin **sonraki** devam etmek için.

    | Ayar | Açıklama |
    | --- | --- |
    | **Komut satırı derleme** | Proje derleme komut satırı belirtir. Derleyici (artı herhangi anahtarlar veya bağımsız değişkenler) adını girin veya projeyi derlemek için kullanmak istediğiniz derleme betikleri. |
    | **Yeniden derle komut satırı** | Yeni proje oluşturur. komut satırı belirtir. |
    | **Temizle komut satırı** | Proje için yapı araçları tarafından oluşturulan destek dosyalarını silmek için komut satırını belirtir. |
    | **Çıkış (hata ayıklama için)** | Projenin hata ayıklama yapılandırması için çıkış dosyalarının dizin yolunu belirtir. |
    | **Önişlemci tanımları (/ D)** | Önişlemci sembolleri tanımlar proje için bkz: [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md). |
    | **Arama Yolu Ekle (/ ı)** | Dizin yolları derleyici arar dosya başvuruları geçirilecek önişlemci yönergeleri, projedeki gidermek için bkz: belirtir [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md). |
    | **Zorunlu eklenen dosyalar (/FI)** | Üst bilgi dosyaları, projeyi derlerken işlemek için bkz belirtir [/FI (zorla dahil dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md). |
    | **.NET bütünleştirilmiş kod arama yolu (/ AI)** | Derleyicinin arama projesinde .NET derleme başvuruları geçirilecek ön işlemci yönergeleri gidermek için bkz: dizin yolları belirtir [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md). |
    | **Zorunlu .NET derlemeleri (/ FU)** | Projeyi derlerken işlemek için bkz: .NET bütünleştirilmiş kodları belirtir [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md). |

    ![Proje yapılandırması](media/config.png)

    > [!NOTE]
    > **Derleme**, **yeniden**, **temiz** komut satırı ve **(hata ayıklama için) çıktı** ayarları yalnızca, etkin **kullanın Dış yapı sistemi** seçeneği seçili **proje ayarlarını belirtme** sayfası.

1. Sürüm yapılandırma ayarlarını belirtin, bu ayarları yapılandırma ayarlarında hata ayıklamayı ile aynıdır. Seçin **son** yeni projeyi oluşturmak için.

    > [!NOTE]
    > Buradan göz atabilirsiniz **hata ayıklama yapılandırması ile aynı** Sihirbazı için hata ayıklama yapılandırması proje ayarları sürüm yapılandırması proje ayarları aynı oluşturacak belirtmek için. Bu seçenek varsayılan olarak denetlenir. Bu kutunun işaretini kaldırın sürece bu sayfadaki diğer tüm seçenekler devre dışıdır.
