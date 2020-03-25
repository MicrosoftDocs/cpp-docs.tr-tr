---
title: Önemli hata C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: e1255578883c8d2bc278184a02575a0a51ed9b6c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204964"
---
# <a name="fatal-error-c1001"></a>Önemli hata C1001

> IÇ DERLEYICI hatası (derleyici dosya *dosyası*, satır *numarası*)

Derleyici, genellikle belirli bir ifadenin veya bir iyileştirme seçeneğinin birleşimi ya da ayrıştırmayla ilgili bir sorun nedeniyle bir yapı için doğru kod üretemiyor. Listelenen derleyici dosyası UTC veya C2 yol segmentine sahipse, büyük olasılıkla bir iyileştirme hatasıdır. Dosyada cxxfe veya c1xx yol segmenti varsa veya msc1. cpp ise, bu büyük olasılıkla bir Ayrıştırıcı hatasıdır. Adlı dosya CL. exe ise, başka bir bilgi yoktur.

Bir veya daha fazla iyileştirme seçeneğini kaldırarak en iyi duruma getirme sorununu giderebilirsiniz. Hangi seçeneğin hata durumunda olduğunu anlamak için, seçenekleri birer birer kaldırın ve hata iletisi kaybolana kadar yeniden derleyin. En yaygın olarak sorumlu olan seçenekler [/OG (Global iyileştirmeler)](../../build/reference/og-global-optimizations.md) ve [/Oi (iç işlevler üret)](../../build/reference/oi-generate-intrinsic-functions.md). Hangi iyileştirme seçeneğinin sorumlu olduğunu belirledikten sonra, [en iyi duruma](../../preprocessor/optimize.md) getirme pragmasını kullanarak hatanın gerçekleştiği işlevin etrafında devre dışı bırakabilir ve modülün geri kalanı için seçeneğini kullanmaya devam edebilirsiniz. İyileştirme seçenekleri hakkında daha fazla bilgi için bkz. [iyileştirme en iyi uygulamaları](../../build/optimization-best-practices.md).

Hata nedeniyle iyileştirmeler sorumlu değilse, hatanın bildirildiği satırı veya bu satırı çevreleyen birkaç kod satırını yeniden yazmayı deneyin. Kodu, ön işlemden sonra derleyicinin gördüğü şekilde görmek için [/p (bir dosyaya ön işlem)](../../build/reference/p-preprocess-to-a-file.md) seçeneğini kullanabilirsiniz.

Hatanın kaynağını yalıtmak ve Microsoft 'a iç derleyici hatası bildirme hakkında daha fazla bilgi için bkz. [Visual C++ araç takımı ile sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).
