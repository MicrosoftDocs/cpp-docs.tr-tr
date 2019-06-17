---
title: /VERBOSE (İlerleme iletilerini yazdır)
ms.date: 06/13/2019
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
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
ms.openlocfilehash: bbf7b5966c741535f26202979cbfd71f839cc537
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141661"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (İlerleme iletilerini yazdır)

Bağlantı işlemi sırasında ilerleme iletilerini çıkış.

## <a name="syntax"></a>Sözdizimi

> **/ VERBOSE**\[ **:** {**CLR**|**ICF**|**INCR** | **LIB**|**REF**|**SAFESEH**|**UNUSEDDELAYLOAD** | **UNUSEDLIBS**}\]

## <a name="remarks"></a>Açıklamalar

Bağlayıcı bağlantı oturumunun ilerleme durumu hakkında bilgi gönderir **çıkış** penceresi. Komut satırında, bilgiler Standart çıkışa gönderilir ve bir dosyaya yönlendirilebilir.

| Seçenek | Açıklama |
| ------------ | ----------------- |
| / VERBOSE | Bağlama işleminin ayrıntılarını görüntüler. |
| / VERBOSE: CLR | Özel bağlayıcı etkinliği hakkındaki bilgileri görüntüler nesneleri ve meta veriler kullanılarak derlenmiş [/CLR](clr-common-language-runtime-compilation.md). |
| /VERBOSE:ICF | Kullanımından kaynaklanan bağlayıcı etkinliği hakkındaki bilgileri görüntüler [/OPT: ICF](opt-optimizations.md). |
| /VERBOSE:INCR | Artımlı bağlantı işlemi hakkındaki bilgileri görüntüler. |
| / VERBOSE: LIB | Kitaplıkları gösteren ilerleme durumu iletilerini görüntüler aranır.<br/> Görüntülenen bilgiler kitaplık arama işlemini içerir. Sembol (ile tam yolu) her kitaplığı ve nesne adını listeler, kitaplık ve ve simgeye başvuran nesnelerin bir listesini çözülüyor. |
| / VERBOSE: BAŞVURU | Kullanımından kaynaklanan bağlayıcı etkinliği hakkındaki bilgileri görüntüler [/OPT: ref](opt-optimizations.md). |
| / VERBOSE: SAFESEH | Ne zaman yapılandırılmış özel durum işleme ile uyumsuz modüller hakkında daha fazla bilgi görüntüler [SAFESEH](safeseh-image-has-safe-exception-handlers.md) belirtilmemiş. |
| / VERBOSE: UNUSEDDELAYLOAD | Her gecikmesi hakkında bilgileri görüntüler görüntüsü oluşturulurken kullanılan sembol yüklü DLL'leri yüklendi. |
| / VERBOSE: UNUSEDLIBS | Görüntü oluşturulduğunda, kullanılmayan tüm kitaplık dosyaları hakkındaki bilgileri görüntüler. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçeneği ekleyin **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
