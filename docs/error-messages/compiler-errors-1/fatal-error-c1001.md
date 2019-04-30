---
title: Önemli hata C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: beb382b9c6ccf80d01f5a0262832e7fb7e1ea0a4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345653"
---
# <a name="fatal-error-c1001"></a>Önemli hata C1001

> İÇ derleyici ERROR(compiler file *file*, line *number*)

Derleyici, ayrıştırma genellikle birlikte belirli bir ifadeye ve iyileştirme seçeneği veya bir sorun nedeniyle bir yapı için doğru kod üretilemiyor. Listelenen derleyici dosyayı bir utc veya C2 yol kesimi varsa, büyük olasılıkla en iyi duruma getirme hatadır. Dosya bir cxxfe veya c1xx yol kesimi yok veya msc1.cpp, büyük olasılıkla ayrıştırıcı bir hatadır. Adlı dosyayı cl.exe var ise, başka hiçbir bilgi kullanılabilir.

Genellikle, bir veya daha fazla iyileştirme seçenekleri kaldırarak bir iyileştirme sorunu düzeltebilirsiniz. Hangi seçeneği hataya neden olduğunu belirlemek için hata iletisini kaybolduktan kadar seçenekler tek bir zaman ve yeniden derleyin kaldırın. En yaygın olarak sorumlu Seçenekler [/Og (Global iyileştirmeler)](../../build/reference/og-global-optimizations.md) ve [(iç işlevler Oluştur) /Oi](../../build/reference/oi-generate-intrinsic-functions.md). Hangi iyileştirme seçeneği sorumludur belirledikten sonra bu hatanın oluştuğu kullanarak işlevi geçici olarak devre dışı bırakabilirsiniz [en iyi duruma getirme](../../preprocessor/optimize.md) pragması ve modül geri kalanı için bu seçeneği kullanmak devam edin. En iyi duruma getirme seçenekleri hakkında daha fazla bilgi için bkz. [en iyi uygulamaları iyileştirme](../../build/optimization-best-practices.md).

En iyi duruma getirme hatası için sorumlu emin değilseniz, burada raporlanan hata satırı veya birkaç satırdaki çevreleyen kod satırlarını yeniden deneyin. Kod derleyici görür, ön işleme sonra biçimini görmek için kullanabileceğiniz [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) seçeneği.

Hatanın kaynağını yalıtmak ve derleyici iç hatası Microsoft'a hakkında daha fazla bilgi için bkz. [Visual C++ araç takımı ile ilgili bir sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).