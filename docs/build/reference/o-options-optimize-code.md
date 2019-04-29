---
title: /O Seçenekler (Kodu İyileştir)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: ffd3023120f1d930a24ccef6fa297594062322df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320428"
---
# <a name="o-options-optimize-code"></a>/O Seçenekler (Kodu İyileştir)

**/O** seçenekleri denetlemek çeşitli yardımcı olacak en iyi duruma getirme maksimum hız veya en küçük boyut için kod oluşturun.

- [/ O1](o1-o2-minimize-size-maximize-speed.md) en küçük boyut kodu iyileştirme birleşimi ayarlar.

- [/ O2](o1-o2-minimize-size-maximize-speed.md) kodunuzun en yüksek hızı için iyileştirme birleşimi ayarlar.

- [/OB](ob-inline-function-expansion.md) satır içi işlev genişletmesi denetler.

- [/Od](od-disable-debug.md) derleme hızlandırmak ve hata ayıklamayı kolaylaştırmak için iyileştirme, devre dışı bırakır.

- [/Og](og-global-optimizations.md) genel iyileştirmeler sağlar.

- [/Oi](oi-generate-intrinsic-functions.md) uygun işlev çağrıları için iç işlevler üretir.

- [/OS](os-ot-favor-small-code-favor-fast-code.md) iyileştirmeler boyutu için en iyi duruma getirme hızına üzerinden derleyicinin söyler.

- [/Ot](os-ot-favor-small-code-favor-fast-code.md) derleyicinin boyutu için iyileştirmeler üzerinden en iyi duruma getirme hızına ayrıcalık tanı (varsayılan ayar) bildirir.

- [/Ox](ox-full-optimization.md) birkaç Otomasyona odaklanarak hız iyileştirmeleri seçen bir birleşimi seçeneğidir. Katı bir alt kümesi olan **/O2** iyileştirmeler.

- [/Oy](oy-frame-pointer-omission.md) için daha hızlı işlev çağrıları çağrı yığınında çerçeve işaretçileri oluşturmayı engeller.

## <a name="remarks"></a>Açıklamalar

Birden çok birleştirebilirsiniz **/O** seçeneklerini tek seçenek deyimi. Örneğin, **/Odi** aynı **/Od /Oi**. Belirli seçenekler birbirini dışlar ve birlikte kullanıldığında bir derleyici hatasına neden. Tek tek görmek **/O** daha fazla bilgi için Seçenekler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
