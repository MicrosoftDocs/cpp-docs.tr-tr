---
title: /ERRORREPORT (Dahili bağlayıcı hatalarını raporla)
description: Microsoft NMAKE komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 5e919d4f7eb59524b9145c8e3e59613e60aef1d2
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257695"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Dahili Bağlayıcı Hatalarını Raporla)

**/Errorreport** seçeneği kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

## <a name="syntax"></a>Sözdizimi

> **/Errorreport:** \[ **none** \| **Prompt** \| **kuyruğu** \| **Gönder** ]

## <a name="remarks"></a>Açıklamalar

**/Errorreport** bağımsız değişkenleri Windows hata bildirimi hizmet ayarları tarafından geçersiz kılınır. Raporlama, Windows Hata Bildirimi tarafından etkinleştirilmişse, bağlayıcı, iç hataların raporlarını otomatik olarak Microsoft 'a gönderir. Windows Hata Bildirimi tarafından devre dışı bırakıldığında hiçbir rapor gönderilmez.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş** Özellik sayfası ' nı açın.

1. **Hata raporlama** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)
