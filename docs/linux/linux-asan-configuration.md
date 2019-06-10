---
title: Linux projeleri adresi temizleyici kullanmak için yapılandırma
description: Nasıl yapılandırılacağını açıklar C++ adresi temizleyici kullanmak için Visual Studio'da Linux projeleri.
ms.date: 06/07/2019
ms.openlocfilehash: 2415e8971614de35f046b699ce99c3822faf9372
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66823571"
---
# <a name="configure-linux-projects-to-use-address-sanitizer"></a>Linux projeleri adresi temizleyici kullanmak için yapılandırma

Visual Studio 2019 içinde sürüm 16.1, Linux projelere AddressSanitizer (IsObject) destek tümleşiktir. IsObject MSBuild tabanlı Linux projeleri ve CMake projeleri için etkinleştirebilirsiniz. Linux (WSL) için Uzak Linux sistemlerinde ve Windows alt sisteminde çalışır.

## <a name="about-asan"></a>IsObject hakkında

IsObject olan bir c çalışma zamanı bellek hatası algılayıcısı /C++ , aşağıdaki hataları yakalar:

- Ücretsiz (Sallantıdaki işaretçi başvurusu sonra) kullanın
- Yığın arabellek taşması
- Yığın arabellek taşması
- Sonra iade kullanın
- Sonra kapsam kullanın
- Başlatma sırası hataları

IsObject bir hata algıladığında, yürütmeyi hemen durdurur. Hata ayıklayıcıda bir IsObject etkin programı çalıştırırsanız, hata, bellek adresi ve hatanın oluştuğu kaynak dosya konumu türünü açıklayan bir ileti görürsünüz:

   ![IsObject hata iletisi](media/asan-error.png)

Ayrıca, çıkış penceresinin hata ayıklama bölmesinde (burada bozuk bellek ayrılan/serbest bırakıldı dahil olmak üzere) tam IsObject çıkış görüntüleyebilirsiniz.

## <a name="enable-asan-for-msbuild-based-linux-projects"></a>IsObject Linux MSBuild tabanlı projeler için etkinleştirin

IsObject Linux MSBuild tabanlı projeler için etkinleştirmek için projeyi sağ **Çözüm Gezgini** seçip **özellikleri**. Ardından, gitmek **yapılandırma özellikleri** > **C /C++**  > **Sanitizers**. IsObject derleyici ve bağlayıcı bayrakları etkinleştirilir ve çalışacak şekilde derlenmesi için projenizi gerektirir.

![IsObject etkinleştirmek için bir MSBuild Projesi](media/msbuild-asan-prop-page.png)

İsteğe bağlı IsObject çalışma zamanı bayrakları giderek geçirebilirsiniz **yapılandırma özellikleri** > **hata ayıklama** > **AddressSanitizer çalışma zamanı bayrakları**. Ekleme veya kaldırma bayrakları için aşağı oka tıklayın.

![Çalışma zamanı bayrakları IsObject yapılandırın](media/msbuild-asan-runtime-flags.png)

## <a name="enable-asan-for-visual-studio-cmake-projects"></a>Visual Studio CMake projeleri için IsObject etkinleştir

CMake için IsObject etkinleştirmek için CMakeLists.txt dosyasına sağ **Çözüm Gezgini** ve **CMake proje ayarlarını**.

Bir Linux yapılandırmasına sahip olduğunuzdan emin olun (örneğin, **Linux hata ayıklama**) iletişim kutusunun sol bölmesinde seçili:

![Linux hata ayıklama yapılandırması](media/linux-debug-configuration.png)

IsObject seçenekleri altındadır **genel**. IsObject çalışma zamanı bayrakları biçiminde girin "bayrak = value" noktalı virgülle ayrılmış.

![Linux hata ayıklama yapılandırması](media/cmake-settings-asan-options.png)

## <a name="install-the-asan-debug-symbols"></a>IsObject hata ayıklama sembolleri yükle

IsObject Tanılama'yı etkinleştirmek için Uzak Linux makinesinin veya WSL yükleme, hata ayıklama simgeleri (dbg libasan) yüklemeniz gerekir. Yüklediğiniz libasan dbg sürümüne, GCC Linux makinenizde yüklü sürümü bağlıdır:

|**IsObject sürümü**|**GCC sürümü**|
| --- | --- |
|libasan0|gcc 4.8|
|libasan2|gcc 5|
|libasan3|gcc-6|
|libasan4|gcc 7|
|libasan5|gcc-8|

Bu komutu kullanarak sahip GCC'ın hangi sürümünün belirleyebilirsiniz:

```bash
gcc --version
```

Libasan dbg ihtiyacınız sürümünü görüntülemek için programınızı çalıştırın ve ardından bakmak **hata ayıklama** bölmesinde **çıkış** penceresi. Yüklenen IsObject sürümünü libasan dbg Linux makinenizde gereken sürümüne karşılık gelir. Kullanabileceğiniz **Ctrl + F** penceresinde "libasan" Aranacak. Örneğin, libasan4 varsa, şöyle bir satır bakın:

```Output
Loaded '/usr/lib/x86_64-linux-gnu/libasan.so.4'. Symbols loaded.
```

Apt ile aşağıdaki komutu kullanın. Linux dağıtım paketlerini IsObject hata ayıklama BITS yükleyebilirsiniz. Bu komut, sürüm 4 yükler:

```bash
sudo apt-get install libasan4-dbg
```

Visual Studio IsObject etkinleştirilirse, üst kısmında ister **hata ayıklama** bölmesinde **çıkış** IsObject hata ayıklama sembolleri yükleme penceresi.
