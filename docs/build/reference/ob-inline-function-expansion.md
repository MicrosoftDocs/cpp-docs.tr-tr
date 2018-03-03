---
title: "-Ob (satır içi işlev genişletmesi) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b83d470eaf6a30698d8c2836620a0688daa35cc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ob-inline-function-expansion"></a>/Ob (Satır İçi İşlev Genişletmesi)

Satır içi genişletme işlevlerin denetler.

## <a name="syntax"></a>Sözdizimi

> /OB {0 | 1 | 2}

## <a name="arguments"></a>Arguments

**0**  
Satır içi genişletme devre dışı bırakır. Varsayılan olarak, tüm işlevlerde derleyicinin tedbirli genişletme oluşursa genellikle olarak bilinir *otomatik satır içi kullanım*.

**1**  
Yalnızca işaretli işlevleri genişlemesi verir [satır içi](../../cpp/inline-functions-cpp.md), `__inline`, veya `__forceinline`, veya sınıf bildiriminde tanımlanmış C++ üye işlevi.

**2**  
Varsayılan değer. Genişletme olarak işaretlenmiş işlevleri sağlayan `inline`, `__inline`, veya `__forceinline`ve derleyici seçer herhangi bir işlev.

**/ Ob2** içinde ne zaman efekt olan [/O1, O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) veya [/Ox (etkinleştirmek en hızlı iyileştirmeler)](../../build/reference/ox-full-optimization.md) kullanılır.

Bu seçeneği kullanarak iyileştirmeler etkinleştirmenizi istemektedir **/O1**, **O2**, **/Ox**, veya **/Og**.  

## <a name="remarks"></a>Açıklamalar

Derleyici, satır içi genişleme seçeneklerine ve anahtar sözcüklerine öneri olarak davranır. Genişletilmiş satır içi işlev olacağını garantisi yoktur. Satır içi genişletme devre dışı bırakabilir, ancak belirli bir işlev satır içi derleyiciye kullanırken bile zorlayamaz `__forceinline` anahtar sözcüğü.

Kullanabileceğiniz `#pragma` [auto_inline](../../preprocessor/auto-inline.md) satır içi genişletme için aday olarak kaldıracağı işlevleri dışlama yönergesi. Ayrıca bkz. `#pragma` [iç](../../preprocessor/intrinsic.md) yönergesi.

> [!NOTE]
> Test çalışmaları profil toplanan bilgileri geçersiz kılmalar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için bkz: [Profile-Guided en iyi duruma getirme](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Genişletme **yapılandırma özellikleri**, **C/C++**seçip **en iyi duruma getirme**.

1. Değiştirme **satır içi işlev genişletmesi** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)