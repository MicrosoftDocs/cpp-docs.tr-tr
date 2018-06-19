---
title: / Qsafe_fp_loads | Microsoft Docs
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1462303f9e178c70a845066bc7a0a3ce78a99e15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378291"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Kayan nokta değerlerini tamsayı taşıma yönergeleri gerektirir ve belirli kayan nokta yük iyileştirmeleri devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Açıklamalar

**/ Qsafe_fp_loads** yalnızca derleyicileri kullanılabilir x86 hedef; x64 veya ARM hedef derleyicileri içinde kullanılabilir değil.

**/ Qsafe_fp_loads** tamsayı taşıma yönergeleri kayan nokta taşıma yönergeler yerine bellek ve MMX arasında veri taşımak için kullanılacak derleyici zorlar kaydeder. Bu seçenek ayrıca kayıt yük iyileştirme değeri bir özel durum yüküne neden olabilir, birden çok denetim yollarında yüklenebilir kayan nokta değerleri için devre dışı bırakır — Örneğin, bir NaN değeri.

Bu seçenek tarafından geçersiz kılınır [/fp: dışında](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** tarafından belirtilen derleyici davranışı kümesini belirtir **/fp: dışında**.

**/ Qsafe_fp_loads** uyumlu değil. [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) ve [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md). Kayan nokta derleyici seçenekleri hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneği girin **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
