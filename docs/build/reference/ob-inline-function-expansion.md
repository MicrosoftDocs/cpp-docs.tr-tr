---
title: -Ob (satır içi işlev genişletmesi) | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6755025ff07d79b7e6086fc8c8a59a3bdebdb777
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725263"
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

**/ Ob2** içinde etkisi yoktur olan [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) veya [/Ox (etkinleştirme en hız iyileştirmelerini)](../../build/reference/ox-full-optimization.md) kullanılır.

Bu seçenek, en iyi duruma getirme kullanarak etkinleştirmenizi istemektedir **/O1**, **/O2**, **/Ox**, veya **/Og**.

## <a name="remarks"></a>Açıklamalar

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. Herhangi bir işlevi satır içi olarak genişletilen olmasını garanti yoktur. Satır içi genişletme devre dışı bırakabilirsiniz, ancak belirli bir işlevi satır içi derleyiciye kullanırken bile zorlayamaz `__forceinline` anahtar sözcüğü.

Kullanabileceğiniz `#pragma` [auto_inline](../../preprocessor/auto-inline.md) işlevleri satır içi genişletme için aday olarak düşünmeniz dışlanacak yönergesi. Ayrıca bkz: `#pragma` [iç](../../preprocessor/intrinsic.md) yönergesi.

> [!NOTE]
> Test çalıştırmalarını profil oluşturmadan toplanan bilgileri geçersiz kılar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **C/C++** seçip **iyileştirme**.

1. Değiştirme **satır içi işlev genişletmesi** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)