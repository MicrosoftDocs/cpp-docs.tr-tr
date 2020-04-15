---
title: Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma
description: Address Sanitizer'ı kullanmak için Visual Studio'daki C++ Linux projelerinin nasıl yapılandırılabildiğini açıklar.
ms.date: 06/07/2019
ms.openlocfilehash: 80e9ab46c948f2062391ae723c3425c435bd4507
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364306"
---
# <a name="configure-linux-projects-to-use-address-sanitizer"></a>Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma

Visual Studio 2019 sürüm 16.1'de AddressSanitizer (ASan) desteği Linux projelerine entegre edilmiştir. Hem MSBuild tabanlı Linux projeleri hem de CMake projeleri için ASan'ı etkinleştirebilirsiniz. Uzak Linux sistemlerinde ve Linux için Windows Alt Sistemi'nde (WSL) çalışır.

## <a name="about-asan"></a>Asan Hakkında

ASan, C/C++ için aşağıdaki hataları yakalayan bir çalışma zamanı bellek hatası detektörüdür:

- Ücretsiz (sarkan işaretçi başvurusu) sonra kullanın
- Yığın arabellek taşma
- Yığın arabellek taşması
- Döndükten sonra kullanın
- Kapsam dan sonra kullanma
- Başlatma sırası hataları

ASan bir hata algıladığında, yürütmeyi hemen durdurur. Hata ayıklamada ASan özellikli bir program çalıştırıyorsanız, hatanın türünü, bellek adresini ve hatanın oluştuğu kaynak dosyadaki konumu açıklayan bir ileti görürsünüz:

   ![ASan hata iletisi](media/asan-error.png)

Ayrıca, çıkış penceresinin Hata Ayıklama bölmesinde tam ASan çıktısını (bozuk belleğin tahsis edildiği/tahsis edildiği yer de dahil olmak üzere) da görüntüleyebilirsiniz.

## <a name="enable-asan-for-msbuild-based-linux-projects"></a>MSBuild tabanlı Linux projeleri için ASan'ı etkinleştirin

> [!NOTE]
> Visual Studio 2019 sürüm 16.4'ten başlayarak, Linux projeleri için AddressSanitizer **Configuration Properties** > **C/C++** > **Enable Address Sanitizer**ile etkinleştirilir.

MSBuild tabanlı Linux projeleri için ASan'ı etkinleştirmek için **Solution Explorer'daki** projeye sağ tıklayın ve **Özellikler'i**seçin. Ardından, **Configuration Properties** > **C/C++** > **Sanitizers'a**gidin. ASan derleyici ve bağlayıcı bayrakları ile etkinleştirilir ve projenizin çalışması için yeniden derlenmesini gerektirir.

![MSBuild projesi için ASan'ı etkinleştirme](media/msbuild-asan-prop-page.png)

**Yapılandırma Özellikleri** > **Adres Hata Ayıklama** > **AdresSanitizer Runtime Bayraklar**gezinerek isteğe bağlı ASan çalışma zamanı bayrakları geçirebilirsiniz. Bayrakları eklemek veya kaldırmak için aşağı ok'u tıklatın.

![ASan çalışma zamanı bayraklarını yapılandırma](media/msbuild-asan-runtime-flags.png)

## <a name="enable-asan-for-visual-studio-cmake-projects"></a>Visual Studio CMake projeleri için ASan'ı etkinleştirin

CMake için ASan'ı etkinleştirmek için **Solution Explorer'daki** CMakeLists.txt dosyasına sağ tıklayın ve **Project için CMake Ayarları'nı**seçin.

İletişim kutusunun sol bölmesinde seçilen bir Linux yapılandırmanız (örneğin, **Linux Hata Ayıklama)** olduğundan emin olun:

![Linux Hata Ayıklama Yapılandırması](media/linux-debug-configuration.png)

ASan seçenekleri **Genel**altındadır. ASan çalışma zamanı bayraklarını "flag=value" biçiminde, yarı iki nokta üst üste ayrılmış olarak girin.

![Linux Hata Ayıklama Yapılandırması](media/cmake-settings-asan-options.png)

## <a name="install-the-asan-debug-symbols"></a>ASan hata ayıklama sembollerini yükleme

ASan tanılamayı etkinleştirmek için, hata ayıklama sembollerini (libasan-dbg) uzak Linux makinenize veya WSL yüklemenize yüklemeniz gerekir. Yüklediğiniz libasan-dbg sürümü, Linux makinenize yüklenen GCC sürümüne bağlıdır:

|**ASan sürümü**|**GCC sürümü**|
| --- | --- |
|libasan0|gcc-4.8|
|libasan2|gcc-5|
|libasan3|gcc-6|
|libasan4|gcc-7|
|libasan5|gcc-8|

Bu komutu kullanarak Hangi GCC sürümüne sahip olduğunuzu belirleyebilirsiniz:

```bash
gcc --version
```

İhtiyacınız olan libasan-dbg sürümünü görüntülemek için programınızı çalıştırın ve ardından **Çıktı** penceresinin **Hata Ayıklama** bölmesine bakın. Yüklenen ASan sürümü Linux makinenizde gerekli libasan-dbg sürümüne karşılık gelir. Pencerede "libasan" aramak için **Ctrl + F** kullanabilirsiniz. Örneğin libasan4'ünvarsa, şöyle bir satır görürsünüz:

```Output
Loaded '/usr/lib/x86_64-linux-gnu/libasan.so.4'. Symbols loaded.
```

Aşağıdaki komutla apt kullanan Linux dağıtımlarına ASan hata ayıklama bitlerini yükleyebilirsiniz. Bu komut sürüm 4 yükler:

```bash
sudo apt-get install libasan4-dbg
```

ASan etkinse, Visual Studio sizi **Çıktı** penceresinin **Hata Ayıklama** bölmesinin en üstündeki ASan hata ayıklama sembollerini yüklemeniz için ister.
