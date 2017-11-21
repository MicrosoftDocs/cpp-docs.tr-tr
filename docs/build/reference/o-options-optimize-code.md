---
title: "-O seçenekler (kodu İyileştir) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs: C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58f8aeda2570fef394b5a47d49c5dda090d8e1ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="o-options-optimize-code"></a>/O Seçenekler (Kodu İyileştir)

**/O** seçeneklerini denetleme çeşitli yardımcı iyileştirmeler en yüksek hızı veya en küçük boyut için kod oluşturma.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) en küçük boyut kodu oluşturmak en iyi duruma getirme bileşimini ayarlar.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) kod en yüksek hızı için en iyi duruma getirir iyileştirmeler birleşimi ayarlar.

- [/OB](../../build/reference/ob-inline-function-expansion.md) satır içi işlev genişletmesi denetler.

- [/Od](../../build/reference/od-disable-debug.md) derleme hızlandırmak ve hata ayıklama basitleştirmek için iyileştirme devre dışı bırakır.

- [/Og](../../build/reference/og-global-optimizations.md) global iyileştirmeler sağlar.

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) uygun işlev çağrıları için iç işlevler oluşturur.

- [/OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) hızı için iyileştirmeler üzerinden boyutu için en iyi duruma getirme favor derleyici söyler.

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) boyutu için en iyi duruma getirme üzerinden hızı için en iyi duruma getirme favor derleyici (varsayılan ayar) söyler.

- [/Ox](../../build/reference/ox-full-optimization.md) birkaç en iyi duruma getirme hızı üzerinde bir vurgulu seçer bir birleşimi seçeneğidir. Katı bir alt kümesidir **O2** en iyi duruma getirme.

- [/Oy](../../build/reference/oy-frame-pointer-omission.md) çerçeve işaretçileri daha hızlı işlev çağrıları çağrı yığınında oluşturulmasını önler.

## <a name="remarks"></a>Açıklamalar

Birden çok birleştirebilirsiniz **/O** tek seçenek deyimi içine seçenekleri. Örneğin, **/Odi** aynı **/Od /Oi**. Belirli seçenekleri karşılıklı olarak birbirini dışlar ve birlikte kullandıysanız derleyici hatası neden olabilir. Tek tek görmek **/O** daha fazla bilgi için Seçenekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)