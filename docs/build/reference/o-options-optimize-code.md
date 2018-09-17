---
title: -O seçenekler (kodu İyileştir) | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c77fd91d63ec79fca87e11a4a02eca157eddf84
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717541"
---
# <a name="o-options-optimize-code"></a>/O Seçenekler (Kodu İyileştir)

**/O** seçenekleri denetlemek çeşitli yardımcı olacak en iyi duruma getirme maksimum hız veya en küçük boyut için kod oluşturun.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) en küçük boyut kodu iyileştirme birleşimi ayarlar.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) kodunuzun en yüksek hızı için iyileştirme birleşimi ayarlar.

- [/OB](../../build/reference/ob-inline-function-expansion.md) satır içi işlev genişletmesi denetler.

- [/Od](../../build/reference/od-disable-debug.md) derleme hızlandırmak ve hata ayıklamayı kolaylaştırmak için iyileştirme, devre dışı bırakır.

- [/Og](../../build/reference/og-global-optimizations.md) genel iyileştirmeler sağlar.

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) uygun işlev çağrıları için iç işlevler üretir.

- [/OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) iyileştirmeler boyutu için en iyi duruma getirme hızına üzerinden derleyicinin söyler.

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) derleyicinin boyutu için iyileştirmeler üzerinden en iyi duruma getirme hızına ayrıcalık tanı (varsayılan ayar) bildirir.

- [/Ox](../../build/reference/ox-full-optimization.md) birkaç Otomasyona odaklanarak hız iyileştirmeleri seçen bir birleşimi seçeneğidir. Katı bir alt kümesi olan **/O2** iyileştirmeler.

- [/Oy](../../build/reference/oy-frame-pointer-omission.md) için daha hızlı işlev çağrıları çağrı yığınında çerçeve işaretçileri oluşturmayı engeller.

## <a name="remarks"></a>Açıklamalar

Birden çok birleştirebilirsiniz **/O** seçeneklerini tek seçenek deyimi. Örneğin, **/Odi** aynı **/Od /Oi**. Belirli seçenekler birbirini dışlar ve birlikte kullanıldığında bir derleyici hatasına neden. Tek tek görmek **/O** daha fazla bilgi için Seçenekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)