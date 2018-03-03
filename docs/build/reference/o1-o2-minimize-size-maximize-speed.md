---
title: "-O1, - O2 (boyutu en aza indir, hızı en üst düzeye) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /o2
- /o1
dev_langs:
- C++
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f880b3cb806efa63299bf6cfa4aab4c72df23817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Boyutu En Aza İndir, Hızı En Yükseğe Çıkart)

Önceden tanımlanmış boyutu etkileyen seçenekleri kümesi ve oluşturulan kod hızına seçer.

## <a name="syntax"></a>Sözdizimi

> / O1  
> / O2

## <a name="remarks"></a>Açıklamalar

**/O1** ve **O2** derleyici seçenekleridir birkaç belirli en iyi duruma getirme seçenekleri aynı anda ayarlamak için hızlı bir şekilde. **/O1** seçenek çoğu durumda en küçük kod oluşturan tek tek en iyi duruma getirme seçenekleri ayarlar. **O2** seçenek çoğu durumda hızlı kod oluşturma seçenekleri ayarlar. **O2** sürüm yapıları için varsayılan seçenektir. Bu tabloda tarafından belirlenen belirli seçenekler gösterilmektedir **/O1** ve **O2**:

|Seçenek|Eşdeğer|
|------------|-------------------|
|**/ O1** (boyutu en aza)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/ O2** (hızı en üst düzeye)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/ O1** ve **O2** karşılıklı olarak birbirini dışlar.

> [!NOTE]  
> **x86 belirli**  
> Bu seçenekler çerçeve işaretçisini atlama kullanıldığı anlamına ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**, açık **C/C++** ve ardından **en iyi duruma getirme** özellik sayfası.

1. Değiştirme **en iyi duruma getirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
[/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md)