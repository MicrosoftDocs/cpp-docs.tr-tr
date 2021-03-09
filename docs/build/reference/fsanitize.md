---
description: /Ftemizleme (Temizleme temizleyiciler) derleyici seçeneği hakkında daha fazla bilgi edinin
title: /ftemizleme (temizleyicilerin etkin hale getirme)
ms.date: 02/24/2021
f1_keywords:
- /fsanitize
- -fsanitize
- /fsanitize=address
- /fsanitize-address-use-after-return
- -fsanitize-address-use-after-return
- /fno-sanitize-address-vcasan-lib
- -fno-sanitize-address-vcasan-lib
helpviewer_keywords:
- /fsanitize [C++]
- -fsanitize=address [C++]
- address sanitizer compiler option [C++]
- /fsanitize-address-use-after-return
- /fno-sanitize-address-vcasan-lib
ms.openlocfilehash: 820d39e54db29a5e06d119cbefc8a1980447e8cc
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470637"
---
# <a name="fsanitize-enable-sanitizers"></a>`/fsanitize` (Temizleyicilerin etkinleştir)

**`/fsanitize`** Temizleyicilerin etkinleştirilmesi için derleyici seçeneklerini kullanın. Visual Studio 2019 16,9 itibariyle desteklenen tek Temizleme, [addresstemizleme](../../sanitizers/asan.md)'dir.

## <a name="syntax"></a>Syntax

> **`/fsanitize=address`**\
> **`/fsanitize-address-use-after-return`**\
> **`/fno-sanitize-address-vcasan-lib`**

## <a name="remarks"></a>Açıklamalar

**`/fsanitize=address`** Derleyici seçeneği, bir güçlü derleyici ve çalışma zamanı teknolojisinin, [zor bulma hatalarını](../../sanitizers/asan.md#error-types)hafif bir şekilde kullanmasına olanak tanıyan [addresstemizlemenize](../../sanitizers/asan.md)olanak sağlar.

**`/fsanitize-address-use-after-return`** Ve **`/fno-sanitize-address-vcasan-lib`** derleyici seçenekleri ve [ `/INFERASANLIBS` (çıkartılan Temizleme libs kullanın)](./inferasanlibs.md) ve **`/INFERASANLIBS:NO`** bağlayıcı seçenekleri, gelişmiş kullanıcılar için destek sunar. Daha fazla bilgi için bkz. [addresstemizleyebilir derleme ve dil başvurusu](../../sanitizers/asan-building.md).

**`/fsanitize`** Seçenekler, Visual Studio 2019 sürüm 16,9 ' den başlayarak kullanılabilir.

### <a name="to-set-the-fsanitizeaddress-compiler-option-in-the-visual-studio-development-environment"></a>**`/fsanitize=address`** Visual Studio geliştirme ortamında derleyici seçeneğini ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin.

1. **Etkinleştir adres Temizleme** özelliğini değiştirin. Etkinleştirmek için **Evet (/ftemizleme = adres)** öğesini seçin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-the-advanced-compiler-options"></a>Gelişmiş derleyici seçeneklerini ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini, **/ftemizleme ze-Address-Use-After-Return** veya **/FNO-Temizleme ze-Address-vcasan-lib** olarak ayarlayın.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)\
[`/INFERASANLIBS` (Çıkartılan Temizleme libs kullanın)](./inferasanlibs.md)\
[Addresstemizme genel bakış](../../sanitizers/asan.md)\
[Adrestemizleme bilinen sorunlar](../../sanitizers/asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](../../sanitizers/asan-building.md)
