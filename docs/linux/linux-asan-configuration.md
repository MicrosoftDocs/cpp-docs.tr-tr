---
title: Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma
description: Adres Temizleme kullanımı için C++ Visual Studio 'da Linux projelerinin nasıl yapılandırılacağını açıklar.
ms.date: 06/07/2019
ms.openlocfilehash: da7197981a431becfc1231dae96f7542062de675
ms.sourcegitcommit: b3d19b5f59f3a5d90c24f9f16c73bad4c5eb6944
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71195894"
---
# <a name="configure-linux-projects-to-use-address-sanitizer"></a>Linux projelerini Adres Temizleyici kullanmak üzere yapılandırma

Visual Studio 2019 sürüm 16,1 ' de, Addresstemizleme (ASan) desteği Linux projeleriyle tümleşiktir. ASan 'ı hem MSBuild tabanlı Linux projeleri hem de CMake projeleri için etkinleştirebilirsiniz. Bu, uzak Linux sistemleri ve Linux için Windows alt sistemi (WSL) üzerinde çalışmaktadır.

## <a name="about-asan"></a>ASan hakkında

ASan, C/C++ için aşağıdaki hataları yakalayan bir çalışma zamanı belleği hata algılayıcısı:

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
> Visual Studio 2019 sürüm 16,4 ' den başlayarak, Linux projeleri için addresstemizme özelliği, **yapılandırma özellikleri** > **C/C++**  > **Etkinleştir adres Temizleme**yoluyla etkinleştirilir.

MSBuild tabanlı Linux projeleri için ASan 'ı etkinleştirmek üzere **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Özellikler**' i seçin. Sonra **yapılandırma özellikleri** > **C/C++**  > **Temizleme**' ye gidin. ASan, derleyici ve bağlayıcı bayrakları aracılığıyla etkinleştirilir ve projenizin iş için yeniden derlenmesi gerekir.

![MSBuild projesi için ASan 'ı etkinleştir](media/msbuild-asan-prop-page.png)

**Yapılandırma özelliklerine** > giderek > , isteğe bağlı asan**çalışma zamanı bayraklarını geçirebilirsiniz.** Bayrak eklemek veya kaldırmak için aşağı oka tıklayın.

![ASan çalışma zamanı bayraklarını yapılandırma](media/msbuild-asan-runtime-flags.png)

## <a name="enable-asan-for-visual-studio-cmake-projects"></a>Visual Studio CMake projeleri için ASan 'ı etkinleştir

CMake için ASan 'ı etkinleştirmek üzere **Çözüm Gezgini** Içindeki CMakeLists. txt dosyasına sağ tıklayın ve **CMake ayarlarını proje için**seçin.

İletişim kutusunun sol bölmesinde bir Linux yapılandırmanızın (örneğin, **Linux-Debug**) seçili olduğundan emin olun:

![Linux hata ayıklama yapılandırması](media/linux-debug-configuration.png)

ASan seçenekleri **genel**' in altındadır. ASan çalışma zamanı bayraklarını noktalı virgülle ayırarak "bayrak = value" biçiminde girin.

![Linux hata ayıklama yapılandırması](media/cmake-settings-asan-options.png)

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
