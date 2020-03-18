---
title: /errorReport (Dahili Derleme Hatalarını Raporla)
description: Microsoft C/C++ derleyici/ERRORREPORT komut satırı seçeneği için başvuru.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: afc366728e62029ffbd3993e2fdd740e3aaf3369
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439889"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Dahili Derleme Hatalarını Raporla)

> [!NOTE]
> **/Errorreport** seçeneği kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

## <a name="syntax"></a>Sözdizimi

> **/errorreport:** \[**none** \| **Prompt** \| **kuyruğu** \| **Gönder** ]

## <a name="remarks"></a>Açıklamalar

Derleyici bir kaynak kodu dosyasını işleyeişce bir iç derleyici hatası (ıCE) oluşur. Bir buz oluştuğunda, derleyici bir çıkış dosyası ya da kodunuzu onarmak için kullanabileceğiniz yararlı bir tanılama üretmez.

**/Errorreport** bağımsız değişkenleri Windows hata bildirimi hizmet ayarları tarafından geçersiz kılınır. Raporlama Windows Hata Bildirimi tarafından etkinleştirilmişse, derleyici, iç hataların raporlarını otomatik olarak Microsoft 'a gönderir. Windows Hata Bildirimi tarafından devre dışı bırakıldığında hiçbir rapor gönderilmez.


### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++**  > **Gelişmiş** Özellik sayfası ' nı açın.

1. **Hata raporlama** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
