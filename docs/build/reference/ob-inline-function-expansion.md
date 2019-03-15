---
title: /Ob (Satır İçi İşlev Genişletmesi)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 6bf16e5725916e81e64d80c0a1f96bf502c8826c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807527"
---
# <a name="ob-inline-function-expansion"></a>/Ob (Satır İçi İşlev Genişletmesi)

İşlevlerin satır içi genişlemeyi denetler.

## <a name="syntax"></a>Sözdizimi

> /OB {0 | 1 | 2}

## <a name="arguments"></a>Arguments

**0**<br/>
Satır içi genişletme devre dışı bırakır. Varsayılan olarak, genişletme derleyicinin tüm işlevlerde ortaya genellikle olarak adlandırılan *auto-inlining*.

**1**<br/>
Olarak işaretlenmiş işlevler yalnızca genişlemesini sağlar [satır içi](../../cpp/inline-functions-cpp.md), `__inline`, veya `__forceinline`, veya bir sınıf bildiriminde tanımlanan C++ üye işlevi.

**2**<br/>
Varsayılan değeri. Genişletme olarak işaretlenmiş işlevler sağlayan `inline`, `__inline`, veya `__forceinline`ve derleyicinin seçtiği diğer işlevleri.

**/ Ob2** içinde etkisi yoktur olan [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](o1-o2-minimize-size-maximize-speed.md) veya [/Ox (etkinleştirme en hız iyileştirmelerini)](ox-full-optimization.md) kullanılır.

Bu seçenek, en iyi duruma getirme kullanarak etkinleştirmenizi istemektedir **/O1**, **/O2**, **/Ox**, veya **/Og**.

## <a name="remarks"></a>Açıklamalar

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. Herhangi bir işlevi satır içi olarak genişletilen olmasını garanti yoktur. Satır içi genişletme devre dışı bırakabilirsiniz, ancak belirli bir işlevi satır içi derleyiciye kullanırken bile zorlayamaz `__forceinline` anahtar sözcüğü.

Kullanabileceğiniz `#pragma` [auto_inline](../../preprocessor/auto-inline.md) işlevleri satır içi genişletme için aday olarak düşünmeniz dışlanacak yönergesi. Ayrıca bkz: `#pragma` [iç](../../preprocessor/intrinsic.md) yönergesi.

> [!NOTE]
> Test çalıştırmalarını profil oluşturmadan toplanan bilgileri geçersiz kılar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **C/C++** seçip **iyileştirme**.

1. Değiştirme **satır içi işlev genişletmesi** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
