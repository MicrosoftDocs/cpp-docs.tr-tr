---
description: Daha fazla bilgi edinin:/DELAY (yük içeri aktarma ayarlarını geciktir)
title: /DELAY (Gecikme yükü içe aktarma ayarları)
ms.date: 01/28/2021
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.openlocfilehash: 0dd6aaaffd378afe4ca7d75180da869b2748d639
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522202"
---
# <a name="delay-delay-load-import-settings"></a>`/DELAY` (Yük içeri aktarma ayarlarını geciktir)

Çalışma zamanında DLL 'lerin gecikmeli yüklemesini denetlemeye yönelik bağlayıcı seçenekleri.

## <a name="syntax"></a>Syntax

> **`/DELAY:UNLOAD`**\
> **`/DELAY:NOBIND`**

## <a name="remarks"></a>Açıklamalar

**`/DELAY`** Seçeneği, dll 'lerin [gecikmeli yüklemesini](linker-support-for-delay-loaded-dlls.md) denetler:

- **`/DELAY:UNLOAD`** Niteleyicisi, gecikme Yükleme Yardımcısı IŞLEVINE dll 'nin açıkça kaldırılmasını desteklememesini söyler. Içeri aktarma adres tablosu (ıAT) orijinal biçimine sıfırlanır, ıAT işaretçilerine geçersiz kılınır ve üzerine yazılmasına neden olur.

   **`/DELAY:UNLOAD`**' Yi seçmezseniz, hiçbir çağrısı [`__FUnloadDelayLoadedDLL`](linker-support-for-delay-loaded-dlls.md#explicitly-unload-a-delay-loaded-dll) başarısız olur.

- **`/DELAY:NOBIND`** Niteleyicisi, bağlayıcının son görüntüde bağlanabilir BIR ıAT içermeyeceğini söyler. Varsayılan olarak, Gecikmeli yüklenen dll 'Ler için bağlanabilir ıAT oluşturulur. Elde edilen görüntü, statik olarak bağlı olamaz. (Bağlanabilir IATS içeren görüntüler yürütmeden önce statik olarak bağlanabilir.) Daha fazla bilgi için bkz [`/BIND`](bind.md) ..

   DLL bağlı ise, yardımcı işlevi, [`GetProcAddress`](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) başvurulan her içeri aktarmaların her birine çağırmak yerine bağlı bilgileri kullanmayı dener. Zaman damgası ya da tercih edilen adres, yüklenen DLL 'deki olanlarla eşleşmezse, yardımcı işlev, ıAT 'nin güncel olmadığını varsayar. Bağlanıat yok gibi devam eder.

   **`/DELAY:NOBIND`** Program görüntünüzün daha büyük olmasına neden olur, ancak DLL 'nin yüklenme süresini hızlandırabilir. DLL 'yi bağlamayı hiç düşünmüyorsanız, **`/DELAY:NOBIND`** bağlı olan IAT 'nin oluşturulmasını engeller.

Yük Gecikmeli dll 'Leri belirtmek için [`/DELAYLOAD`](delayload-delay-load-import.md) seçeneğini kullanın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Yüklenen dll 'Yi geciktir** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)
