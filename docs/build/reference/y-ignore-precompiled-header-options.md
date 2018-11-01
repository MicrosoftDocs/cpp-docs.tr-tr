---
title: /Y (Önceden Derlenmiş Üst Bilgi Seçeneklerini Yoksay)
ms.date: 11/04/2016
f1_keywords:
- /y-
helpviewer_keywords:
- Y- compiler option [C++]
- -Y- compiler option [C++]
- /Y- compiler option [C++]
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
ms.openlocfilehash: 8de7de7a4164916b9662e3a78fe00dd0a40cecc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542911"
---
# <a name="y--ignore-precompiled-header-options"></a>/Y (Önceden Derlenmiş Üst Bilgi Seçeneklerini Yoksay)

Tüm diğer nedenler `/Y` derleyici seçeneklerini yok sayılacak (ve kendisini geçersiz kılınamaz).

## <a name="syntax"></a>Sözdizimi

```
/Y-
```

## <a name="remarks"></a>Açıklamalar

Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz:

- [/Y (Önceden Derlenmiş Üst Bilgiler)](../../build/reference/y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)