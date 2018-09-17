---
title: -GZ (etkinleştirme yığın çerçevesi çalışma zamanı hata denetimini) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gz
dev_langs:
- C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f13824064b7c7dcdb75524a22b14a4d90942918
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707232"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Yığın Çerçevesi Çalışma Zamanı Hata Denetimini Etkinleştir)

Aynı işlemleri gerçekleştirir [/RTC (çalışma zamanı hata denetimleri)](../../build/reference/rtc-run-time-error-checks.md) seçeneği. Kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```
/GZ
```

## <a name="remarks"></a>Açıklamalar

**/GZ** yalnızca bir nonoptimized kullanmak içindir ([/Od (devre dışı bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md)) oluşturun.

**/GZ** itibaren Visual Studio 2005; kullanım dışı kullanın [/RTC (çalışma zamanı hata denetimleri)](../../build/reference/rtc-run-time-error-checks.md) yerine. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)