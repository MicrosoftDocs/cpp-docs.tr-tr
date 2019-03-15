---
title: / Diagnostics (derleyici tanılama seçenekleri)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 6b7d043e00204fa191530f03bbed069d71a25fc5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822318"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/ Diagnostics (derleyici tanılama seçenekleri)

Kullanım **/Diagnostics** konum bilgilerini hata ve uyarı görünümünü belirtmek için derleyici seçeneği.

## <a name="syntax"></a>Sözdizimi

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017 ve sonraki sürümlerde desteklenir.

**/Diagnostics** derleyici seçeneği, hata ve uyarı bilgilerini görünümünü denetler.

**/Diagnostics:classic** raporları nereye sorunu bulundu satır numarasını varsayılan seçenektir.

**/Diagnostics:column** seçeneği de burada sorunu bulundu sütun içerir. Bu soruna neden olan karakter ya da belirli bir dil yapısı belirlemenize yardımcı olabilir.

**/Diagnostics:caret** seçeneği nerede sorun bulundu ve bir şapka (^) sorunun algılandığı yere kod satırı altında konuma yerleştirir sütun içerir.

Bazı durumlarda, derleyicinin bir sorun oluştuğu algılamaz unutmayın. Örneğin, diğer, beklenmeyen sembolleri karşılaştı kadar eksik noktalı virgül algılanamayabilir. Sütun bildirilir ve giriş işaretini derleyici bir şey her zaman düzeltmenizi yapmak gerek duyduğunuz değil yanlış olduğunu algılandığı yere yerleştirilir.

**/Diagnostics** seçenek, Visual Studio 2017'den itibaren kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizin açın **özellik sayfaları** iletişim kutusu.

1. Altında **yapılandırma özellikleri**, genişletme **C/C++** klasörü seçin **genel** özellik sayfası.

1. Dropdown denetimi kullanın **tanılama biçimi** bir tanılama seçmek için alan görüntü seçeneği. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
