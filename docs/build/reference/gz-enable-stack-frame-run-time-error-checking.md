---
title: /GZ (Yığın Çerçevesi Çalışma Zamanı Hata Denetimini Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 3e6ffce487cc8183e45f3a911e7060ea22b28216
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292066"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Yığın Çerçevesi Çalışma Zamanı Hata Denetimini Etkinleştir)

Aynı işlemleri gerçekleştirir [/RTC (çalışma zamanı hata denetimleri)](rtc-run-time-error-checks.md) seçeneği. Kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```
/GZ
```

## <a name="remarks"></a>Açıklamalar

**/GZ** yalnızca bir nonoptimized kullanmak içindir ([/Od (devre dışı bırak (Hata Ayıkla))](od-disable-debug.md)) oluşturun.

**/GZ** itibaren Visual Studio 2005; kullanım dışı kullanın [/RTC (çalışma zamanı hata denetimleri)](rtc-run-time-error-checks.md) yerine. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
