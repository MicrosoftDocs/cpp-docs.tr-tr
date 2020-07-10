---
title: /O seçenekler (Kodu iyileştir)
description: MSVC/O derleyici seçenekleri kullanılacak derleyici iyileştirmelerini belirtir.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: 36ef582787a3ec2d7aee1e589c70b48712d9d552
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180883"
---
# <a name="o-options-optimize-code"></a>`/O`Seçenekler (kodu Iyileştirme)

**`/O`** Seçenekler, en yüksek hız veya minimum boyut için kod oluşturmanıza yardımcı olan çeşitli iyileştirmeleri denetler.

- [`/O1`](o1-o2-minimize-size-maximize-speed.md)Minimum boyut kodu üreten iyileştirmelerin birleşimini ayarlar.

- [`/O2`](o1-o2-minimize-size-maximize-speed.md)en yüksek hız için kodu en iyi duruma getirme iyileştirmeleri bileşimini ayarlar.

- [`/Ob`](ob-inline-function-expansion.md)satır içi işlev genişletmeyi denetler.

- [`/Od`](od-disable-debug.md)derlemeyi hızlandırmak ve hata ayıklamayı basitleştirmek için iyileştirmeyi devre dışı bırakır.

- [`/Og`](og-global-optimizations.md)(kullanım dışı) genel iyileştirmeleri sunar.

- [`/Oi`](oi-generate-intrinsic-functions.md)uygun işlev çağrıları için iç işlevler üretir.

- [`/Os`](os-ot-favor-small-code-favor-fast-code.md)derleyiciye, hız için iyileştirmelerin en iyileştirmeleri üzerinde en iyileştirmeleri kullanmasını söyler.

- [`/Ot`](os-ot-favor-small-code-favor-fast-code.md)(varsayılan ayar) derleyiciye boyut iyileştirmelerinin hızına ilişkin hızlara ilişkin iyileştirmeleri tercih vermesini söyler.

- [`/Ox`](ox-full-optimization.md), hızlı bir şekilde vurgu sağlayan bir dizi iyileştirmelerin seçtiği bir bileşim seçenektir. **`/Ox`** iyileştirmelerin katı bir alt kümesidir **`/O2`** .

- [`/Oy`](oy-frame-pointer-omission.md)daha hızlı işlev çağrıları için çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

## <a name="remarks"></a>Açıklamalar

Birden çok seçeneği **`/O`** tek bir seçenek ifadesinde birleştirebilirsiniz. Örneğin, **`/Odi`** ile aynıdır **`/Od /Oi`** . Bazı seçenekler birbirini dışlamalı ve birlikte kullanılırsa derleyici hatasına neden olur. Daha fazla bilgi için bkz. bireysel **`/O`** Seçenekler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
