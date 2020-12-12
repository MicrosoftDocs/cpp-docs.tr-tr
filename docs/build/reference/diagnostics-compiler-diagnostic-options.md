---
description: Daha fazla bilgi edinin:/Diagnostics (derleyici tanılama seçenekleri)
title: /Diagnostics (derleyici tanılama seçenekleri)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 2c34edc0374e59720eb05e97379702833efaa703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201423"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/Diagnostics (derleyici tanılama seçenekleri)

Hata ve uyarı konumu bilgilerinin görüntülenmesini belirtmek için **/Diagnostics** derleyici seçeneğini kullanın.

## <a name="syntax"></a>Syntax

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017 ve üzeri sürümlerde desteklenir.

**/Diagnostics** derleyici seçeneği hata ve uyarı bilgilerinin görüntülenmesini denetler.

**/Diagnostics: Classic** seçeneği, yalnızca sorunun bulunduğu satır numarasını raporlayan varsayılan seçenektir.

**/Diagnostics: Column** seçeneği, sorunun bulunduğu sütunu da içerir. Bu, soruna neden olan belirli dil yapısını veya karakteri belirlemenize yardımcı olabilir.

**/Diagnostics: şapka** seçeneği, sorunun bulunduğu sütunu içerir ve sorunun algılandığı kod satırındaki konumun altına bir şapka (^) koyar.

Bazı durumlarda derleyicinin gerçekleştiği bir sorunu algılamadığına unutmayın. Örneğin, eksik noktalı virgül, diğer bir deyişle, beklenmeyen simgelerle karşılaşmayabilir. Sütun raporlanır ve şapka, derleyicinin bir şeyin yanlış olduğunu algıladığı, her zaman düzeltmeyi yapmanız gereken her yerde yer aldığı yerde yer alır.

**/Diagnostics** seçeneği Visual Studio 2017 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri** altında **C/C++** klasörünü genişletin ve **genel** özellik sayfasını seçin.

1. Tanılama görüntü seçeneğini belirlemek için **Tanılama biçimi** alanında açılan menü denetimini kullanın. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
