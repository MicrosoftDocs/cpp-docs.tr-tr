---
description: Daha fazla bilgi edinin:/VERBOSE (ilerleme iletilerini Yazdır)
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
ms.openlocfilehash: 9d1a22a1b05f42a707b2449fbb114ba06db85ff5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176424"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (İlerleme iletilerini yazdır)

Bağlantı işlemi sırasında ilerleme iletisi çıkışları.

## <a name="syntax"></a>Syntax

> **/Verbose** \[ **:**{**clr** | **ICF** | **INR** | **LIB** | **ref** | **SafeSEH** | **UNUSEDDELAYLOAD** | **UNUSEDLIBS**}\]

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, bağlama oturumunun ilerleme durumu hakkında bilgileri **Çıkış** penceresine gönderir. Komut satırında, bilgiler standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

| Seçenek | Açıklama |
| ------------ | ----------------- |
| /VERBOSE | Bağlama işlemiyle ilgili ayrıntıları görüntüler. |
| /VERBOSE: CLR | [/Clr](clr-common-language-runtime-compilation.md)kullanılarak derlenen nesnelere ve meta verilere özel bağlayıcı etkinliği hakkındaki bilgileri görüntüler. |
| /VERBOSE: ıCF | [/OPT: ICF](opt-optimizations.md)'nin kullanılması sonucunda oluşan bağlayıcı etkinliğiyle ilgili bilgileri görüntüler. |
| /VERBOSE: INCR | Artımlı bağlantı işlemiyle ilgili bilgileri görüntüler. |
| /VERBOSE: LIB | Yalnızca aranan kitaplıkları gösteren ilerleme mesajlarını görüntüler.<br/> Görünen bilgiler, kitaplık arama işlemini içerir. Her bir kitaplığı ve nesne adını (tam yol ile), kitaplıktan çözümlenen simgeyi ve sembole başvuruda bulunan nesnelerin bir listesini listeler. |
| /VERBOSE: REF | [/OPT: ref](opt-optimizations.md)kullanımını belirten bağlayıcı etkinliği hakkındaki bilgileri görüntüler. |
| /VERBOSE: SAFESEH | [/SafeSEH](safeseh-image-has-safe-exception-handlers.md) belirtilmediğinde güvenli yapılandırılmış özel durum işleme ile uyumsuz modüllerle ilgili bilgileri görüntüler. |
| /VERBOSE: UNUSEDDELAYLOAD | Görüntü oluşturulduğunda kullanılan herhangi bir simge olmayan Gecikmeli yüklenen dll 'Ler hakkındaki bilgileri görüntüler. |
| /VERBOSE: UNUSEDLIBS | Görüntü oluşturulduğunda kullanılmayan tüm kitaplık dosyaları hakkındaki bilgileri görüntüler. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. Seçeneği **ek seçenekler** kutusuna ekleyin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
