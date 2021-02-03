---
description: Daha fazla bilgi edinin:/VERBOSE (ilerleme iletilerini Yazdır)
title: /VERBOSE (İlerleme iletilerini yazdır)
ms.date: 02/03/2021
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.openlocfilehash: d58a6cc8d75021c78f8161cf12957a77bb26483c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522930"
---
# <a name="verbose-print-progress-messages"></a>`/VERBOSE` (İlerleme iletilerini Yazdır)

Bağlantı işlemi sırasında ilerleme iletisi çıkışları.

## <a name="syntax"></a>Syntax

> **`/VERBOSE`**\[**`:`**{**`CLR`**|**`ICF`**|**`INCR`**|**`LIB`**|**`REF`**|**`SAFESEH`**|**`UNUSEDDELAYLOAD`**|**`UNUSEDLIBS`**}\]

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, bağlama oturumunun ilerleme durumu hakkında bilgileri **Çıkış** penceresine gönderir. Komut satırında, bilgiler standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

| Seçenek | Açıklama |
| ------------ | ----------------- |
| **`/VERBOSE`** | Bağlama işlemiyle ilgili ayrıntıları görüntüler. |
| **`/VERBOSE:CLR`** | Kullanılarak derlenen nesnelere ve meta verilere özel bağlayıcı etkinliği hakkındaki bilgileri görüntüler [`/clr`](clr-common-language-runtime-compilation.md) . |
| **`/VERBOSE:ICF`** | Kullanımı sonucu olan bağlayıcı etkinliğiyle ilgili bilgileri görüntüler [`/OPT:ICF`](opt-optimizations.md) . |
| **`/VERBOSE:INCR`** | Artımlı bağlantı işlemiyle ilgili bilgileri görüntüler. |
| **`/VERBOSE:LIB`** | Yalnızca aranan kitaplıkları gösteren ilerleme mesajlarını görüntüler.<br/> Görünen bilgiler, kitaplık arama işlemini içerir. Her bir kitaplığı ve nesne adını (tam yol ile), kitaplıktan çözümlenen simgeyi ve sembole başvuruda bulunan nesnelerin bir listesini listeler. |
| **`/VERBOSE:REF`** | Kullanımı sonucu olan bağlayıcı etkinliğiyle ilgili bilgileri görüntüler [`/OPT:REF`](opt-optimizations.md) . |
| **`/VERBOSE:SAFESEH`** | Belirtilmediğinde, güvenli yapılandırılmış özel durum işleme ile uyumsuz modüllerle ilgili bilgileri görüntüler [`/SAFESEH`](safeseh-image-has-safe-exception-handlers.md) . |
| **`/VERBOSE:UNUSEDDELAYLOAD`** | Görüntü oluşturulduğunda kullanılan herhangi bir simge olmayan Gecikmeli yüklenen dll 'Ler hakkındaki bilgileri görüntüler. |
| **`/VERBOSE:UNUSEDLIBS`** | Görüntü oluşturulduğunda kullanılmayan tüm kitaplık dosyaları hakkındaki bilgileri görüntüler. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. Seçeneği **ek seçenekler** kutusuna ekleyin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
