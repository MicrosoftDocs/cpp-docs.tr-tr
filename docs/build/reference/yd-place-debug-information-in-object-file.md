---
description: Daha fazla bilgi edinin:/yd (hata ayıklama bilgilerini nesne dosyasına yerleştir)
title: /Yd (Hata Ayıklama Bilgilerini Nesne Dosyasına Yerleştir)
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: 7716d5ca1893faefac9186f97e2f7439a3887343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243594"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Hata Ayıklama Bilgilerini Nesne Dosyasına Yerleştir)

Paces, [/Yıc](yc-create-precompiled-header-file.md) ve [/Z7](z7-zi-zi-debug-information-format.md) seçenekleriyle birlikte kullanıldığında önceden derlenmiş üst bilgi (. pch) dosyasından oluşturulan tüm nesne dosyalarındaki hata ayıklama bilgilerini tamamlar. Kullanım dışı.

## <a name="syntax"></a>Syntax

```
/Yd
```

## <a name="remarks"></a>Açıklamalar

**/Yd** kullanım dışıdır; Visual C++ artık tek bir. pdb dosyasına yazılan birden çok nesneyi destekliyor, bunun yerine **/Zi** kullanın. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

Hata ayıklama bilgilerini içeren bir kitaplığı dağıtmanız gerekmiyorsa, **/Z7** ve **/yd** yerine [/zı](z7-zi-zi-debug-information-format.md) seçeneğini kullanın.

Tüm hata ayıklama bilgilerini her. obj dosyasında depolamak yalnızca hata ayıklama bilgilerini içeren kitaplıkları dağıtmak için gereklidir. Derlemeyi yavaşlatır ve önemli miktarda disk alanı gerektirir. **/Yıc** ve **/Z7** , **/yd** olmadan kullanıldığında, derleyici ortak hata ayıklama bilgilerini. pch dosyasından oluşturulan ilk. obj dosyasında depolar. Derleyici, bu bilgileri daha sonra. pch dosyasından oluşturulan. obj dosyalarına eklemez; bilgilere çapraz başvurular ekler. Kaç. obj dosyası. pch dosyasını kullanırken olsun, yalnızca bir. obj dosyası ortak hata ayıklama bilgilerini içerir.

Bu varsayılan davranış daha hızlı derleme süreleriyle sonuçlanır ve disk alanı taleplerini azaltsa da, küçük bir değişikliğin ortak hata ayıklama bilgilerini içeren. obj dosyasını yeniden oluşturması gerekiyorsa, bu durum günceldir. Bu durumda, derleyici özgün. obj dosyasına çapraz başvurular içeren tüm. obj dosyalarını yeniden oluşturulmalıdır. Ayrıca, ortak bir. pch dosyası farklı projeler tarafından kullanılıyorsa, tek bir. obj dosyasına çapraz başvuruların rahatlaştırılması zordur.

Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz.

- [/Y (önceden derlenmiş üst bilgiler)](y-precompiled-headers.md)

- [Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Örnekler

Her biri bu **#include** deyimlerini Içeren, F. cpp ve G. cpp iki temel dosyasına sahip olduğunuzu varsayalım:

```
#include "windows.h"
#include "etc.h"
```

Aşağıdaki komut, ön derlenmiş üstbilgi dosyasını ve. pch ve nesne dosyası olan F. obj ' i oluşturur:

```
CL /YcETC.H /Z7 F.CPP
```

F. obj nesne dosyası, WINDOWS. h ve vb. h (ve içerdikleri diğer tüm üstbilgi dosyaları) için tür ve sembol bilgilerini içerir. Artık, kaynak dosyayı G. cpp derlemek için önceden derlenmiş üst bilgi vb. pch 'yi kullanabilirsiniz:

```
CL /YuETC.H /Z7 G.CPP
```

G. obj nesne dosyası, ön derlenmiş üst bilgi için hata ayıklama bilgilerini içermez, ancak yalnızca F. obj dosyasındaki bu bilgilere başvurur. F. obj dosyasıyla bağlantı oluşturmanız gerektiğini unutmayın.

Önceden derlenmiş üst bilgi, **/Z7** ile derlenmişse, yine de **/Z7** kullanarak daha sonraki Derlemelerle kullanabilirsiniz. Ancak, hata ayıklama bilgileri geçerli nesne dosyasına yerleştirilir ve önceden derlenmiş üst bilgide tanımlanan işlevlerin ve türlerin yerel sembolleri hata ayıklayıcı için kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
