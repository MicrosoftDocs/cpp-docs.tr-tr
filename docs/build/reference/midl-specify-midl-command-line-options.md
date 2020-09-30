---
title: /MIDL (MIDL Komut Satırı Seçeneklerini Belirt)
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: 3f1b6526f51e5aaa48008792361d3e63249d9f16
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502860"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)

MıDL komut satırı seçenekleri için bir yanıt dosyası belirtir

## <a name="syntax"></a>Sözdizimi

> **/MIDL: \@ ** <em>Dosya</em>

## <a name="arguments"></a>Arguments

*dosyasýný*<br/>
[MIDL komut satırı seçeneklerini](/windows/win32/Midl/general-midl-command-line-syntax)içeren dosyanın adı.

## <a name="remarks"></a>Açıklamalar

Bir IDL dosyasını bir TLB dosyasına dönüştürmeye yönelik tüm seçenekler *dosyada*verilmelidir; MıDL komut satırı seçenekleri bağlayıcının komut satırında belirtilemez. /MıDL belirtilmemişse, MıDL derleyicisi yalnızca IDL dosya adı ve başka hiçbir seçenek olmadan çağrılır.

Dosya, her satır için bir MıDL komut satırı seçeneği içermelidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **katıştırılmış IDL** özellik sayfasını seçin.

1. **MIDL Commands** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/IDLOUT (MıDL çıktı dosyalarını Adlandır)](idlout-name-midl-output-files.md)<br/>
[/IGNOREıDL (öznitelikleri MıDL 'ye Işleme)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLHAKKıNDA (ad. TLB dosyası)](tlbout-name-dot-tlb-file.md)<br/>
[Öznitelikli Program Oluşturma](../../windows/attributes/cpp-attributes-com-net.md)
