---
title: Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma
description: Adres Temizleme kullanımı için Visual Studio 'da C++ Linux projelerinin nasıl yapılandırılacağını açıklar.
ms.date: 09/25/2020
ms.openlocfilehash: 7e68d0af4d2ab27820f894bafc58bed444f141d9
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414211"
---
# <a name="configure-linux-projects-to-use-address-sanitizer"></a>Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma

Visual Studio 2019 sürüm 16,1 ' de, Addresstemizleme (ASan) desteği Linux projeleriyle tümleşiktir. ASan 'ı hem MSBuild tabanlı Linux projeleri hem de CMake projeleri için etkinleştirebilirsiniz. Bu, uzak Linux sistemleri ve Linux için Windows alt sistemi (WSL) üzerinde çalışmaktadır.

## <a name="about-asan"></a>ASan hakkında

ASan, C/C++ için bir çalışma zamanı bellek hatası algılayıcısının aşağıdaki hataları yakalar:

- Ücretsiz (Dangling işaretçi başvurusu) sonra kullanın
- Yığın arabelleği taşması
- Yığın arabelleği taşması
- Döndürmeden sonra kullan
- Kapsamdan sonra kullan
- Başlatma sırası hataları

ASan bir hata algıladığında, yürütmeyi hemen sonlandırır. Hata ayıklayıcıda ASan özellikli bir programı çalıştırırsanız hata türünü, bellek adresini ve hatanın oluştuğu kaynak dosyadaki konumu açıklayan bir ileti görürsünüz:

   ![ASan hata iletisi](media/asan-error.png)

Ayrıca, çıkış penceresinin hata ayıklama bölmesinde tam ASan çıkışını (bozuk belleğin ayrıldığı/serbest bırakıldığı dahil olmak üzere) görüntüleyebilirsiniz.

## <a name="enable-asan-for-msbuild-based-linux-projects"></a>MSBuild tabanlı Linux projeleri için ASan 'ı etkinleştir

> [!NOTE]
> Visual Studio 2019 sürüm 16,4 ' den başlayarak, Linux projeleri için addresstemizleme özelliği, **Proje özellikleri**  >  **yapılandırma özellikleri**  >  **C/C++**  >  **Etkinleştir adres Temizleme**özelliği aracılığıyla etkinleştirilir.

MSBuild tabanlı Linux projeleri için ASan 'ı etkinleştirmek üzere **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Özellikler**' i seçin. Ardından, **yapılandırma özellikleri**  >  **C/C++**  >  **temizleyiciler**' a gidin. ASan, derleyici ve bağlayıcı bayrakları aracılığıyla etkinleştirilir ve projenizin iş için yeniden derlenmesi gerekir.

![MSBuild projesi için ASan 'ı etkinleştir](media/msbuild-asan-prop-page.png)

**Yapılandırma özelliklerine**giderek, isteğe bağlı asan çalışma zamanı bayraklarını geçirebilirsiniz  >  **Debugging**  >  **AddressSanitizer Runtime Flags**. Bayrak eklemek veya kaldırmak için aşağı oka tıklayın.

![ASan çalışma zamanı bayraklarını yapılandırma](media/msbuild-asan-runtime-flags.png)

## <a name="enable-asan-for-visual-studio-cmake-projects"></a>Visual Studio CMake projeleri için ASan 'ı etkinleştir

CMake için ASan 'ı etkinleştirmek üzere, **Çözüm Gezgini** CMakeLists.txt dosyasına sağ tıklayın ve **Proje Için CMake ayarları**' nı seçin.

İletişim kutusunun sol bölmesinde bir Linux yapılandırmanızın (örneğin, **Linux-Debug**) seçili olduğundan emin olun:

![Yapılandırma seçeneklerinden biri olarak listelenen Linux hata ayıklamanın sol bölmesinin ekran görüntüsü.](media/linux-debug-configuration.png)

ASan seçenekleri **genel**' in altındadır. ASan çalışma zamanı bayraklarını boşluklarla ayırarak "bayrak = değer" biçiminde girin. Kullanıcı arabirimi, noktalı virgül kullanmayı yanlış bir şekilde önerir. Bayrakları ayırmak için boşluk veya iki nokta üst üste kullanın.

![Adres Temizleme çalışma zamanı bayraklarını gösteren adres Temizleme seçeneğini etkinleştir seçeneğinin ekran görüntüsü.](media/cmake-settings-asan-options.png)

## <a name="install-the-asan-debug-symbols"></a>ASan hata ayıklama sembollerini yükler

ASan tanılamayı etkinleştirmek için, uzak Linux makinenize veya WSL yüklemenize hata ayıklama sembollerini (libasan-DBG) yüklemeniz gerekir. Yüklediğiniz libasan-DBG sürümü, Linux makinenizde yüklü GCC sürümüne bağlıdır:

|**ASan sürümü**|**GCC sürümü**|
| --- | --- |
|libasan0|GCC-4,8|
|libasan2|GCC-5|
|libasan3|GCC-6|
|libasan4|GCC-7|
|libasan5|GCC-8|

Bu komutu kullanarak hangi GCC sürümünü kullandığınızı belirleyebilirsiniz:

```bash
gcc --version
```

İhtiyacınız olan libasan-DBG sürümünü görüntülemek için programınızı çalıştırın ve ardından **Çıkış** penceresinin **hata ayıklama** bölmesine bakın. Yüklenen ASan sürümü, Linux makinenizde gereken libasan-DBG sürümüne karşılık gelir. Pencerede "libasan" aramak için **CTRL + F** ' i kullanabilirsiniz. Örneğin, libasan4 varsa şöyle bir satır görürsünüz:

```Output
Loaded '/usr/lib/x86_64-linux-gnu/libasan.so.4'. Symbols loaded.
```

Asan hata ayıklama bitlerini aşağıdaki komutla apt kullanan Linux Distro 'lara 'ye yükleyebilirsiniz. Bu komut sürüm 4 ' ü yüklüyor:

```bash
sudo apt-get install libasan4-dbg
```

ASan etkinleştirilirse, Visual Studio, ASan hata ayıklama sembollerini yüklemek için **Çıkış** penceresinin **hata ayıklama** bölmesinin en üstünde sizi uyarır.
