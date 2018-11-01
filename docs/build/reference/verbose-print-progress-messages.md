---
title: /VERBOSE (İlerleme İletilerini Yazdır)
ms.date: 11/04/2016
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
ms.openlocfilehash: 41a8ee835a65a7c9a17df9bb9c155267cae29baf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575623"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (İlerleme İletilerini Yazdır)

```
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcı bağlantı oturumunun ilerleme durumu hakkında bilgi gönderir **çıkış** penceresi. Komut satırında, bilgiler Standart çıkışa gönderilir ve bir dosyaya yönlendirilebilir.

|Seçenek|Açıklama|
|------------|-----------------|
|/ VERBOSE|Bağlama işleminin ayrıntılarını görüntüler.|
|/ VERBOSE: ICF|Kullanımından kaynaklanan bağlayıcı etkinliği hakkındaki bilgileri görüntüleme [/OPT: ICF](../../build/reference/opt-optimizations.md).|
|/ VERBOSE: INCR|Artımlı bağlantı işlemi hakkındaki bilgileri görüntüler.|
|/ VERBOSE: LIB|Kitaplıkları gösteren ilerleme durumu iletilerini görüntüler aranır.<br /><br /> Görüntülenen bilgiler kitaplık arama işlemini içerir ve (ile tam yolu) her kitaplığı ve nesne adını listeler, sembol kitaplığı ve ve simgeye başvuran nesnelerin bir listesini çözülüyor.|
|/ VERBOSE: BAŞVURU|Kullanımından kaynaklanan bağlayıcı etkinliği hakkındaki bilgileri görüntüler [/OPT: ref](../../build/reference/opt-optimizations.md).|
|/ VERBOSE: SAFESEH|Ne zaman güvenli özel durum işleme ile uyumlu olmayan modüller hakkında daha fazla bilgi görüntüler [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) belirtilmedi.|
|/ VERBOSE: UNUSEDLIBS|Görüntü oluşturulduğunda, kullanılmayan tüm kitaplık dosyaları hakkındaki bilgileri görüntüler.|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Genişletin **bağlayıcı** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Seçeneği ekleyin **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)