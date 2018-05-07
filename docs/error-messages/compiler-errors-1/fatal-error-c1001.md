---
title: Önemli hata C1001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1001
dev_langs:
- C++
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f605dd7e4892c4a8b57e544ed857257be72f020d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1001"></a>Önemli hata C1001

> İÇ derleyici ERROR(compiler file *file*, line *number*)  
  
Derleyici genellikle belirli bir ifade ve en iyi duruma getirme seçeneği veya bir sorunu bileşimi nedeniyle bir yapı için doğru kodu ayrıştırma oluşturulamıyor. Listelenen derleyici dosya utc veya C2 yol kesimi varsa, büyük olasılıkla en iyi duruma getirme hatadır. Dosya cxxfe veya c1xx yol kesimi yok veya msc1.cpp, büyük olasılıkla ayrıştırıcı bir hatadır. Adlı dosyayı cl.exe ise, başka hiçbir bilgi mevcut değil.  

Genellikle, bir veya daha fazla en iyi duruma getirme seçenekleri kaldırarak bir en iyi duruma getirme sorunu düzeltebilirsiniz. Hangi seçeneği hataya neden olduğunu belirlemek için hata iletisi kaybolduktan kadar seçenekleri birer bir saat ve yeniden derleyebilirsiniz kaldırın. En yaygın olarak sorumlu seçeneklerdir [/Og (Global iyileştirmeler)](../../build/reference/og-global-optimizations.md) ve [/Oi (iç işlevler Oluştur)](../../build/reference/oi-generate-intrinsic-functions.md). Hangi iyileştirme seçeneği sorumludur belirledikten sonra bu hatanın oluştuğu kullanarak işlevi geçici devre dışı bırakabilirsiniz [en iyi duruma getirme](../../preprocessor/optimize.md) pragma ve modül geri kalanı için bu seçeneği kullanmak devam edin. En iyi duruma getirme seçenekleri hakkında daha fazla bilgi için bkz: [en iyi uygulamaları iyileştirme](../../build/reference/optimization-best-practices.md).

En iyi duruma getirme hatası için sorumlu emin değilseniz, burada bildirilen hata, veya birkaç satıra bu satırı çevreleyen kodunun yeniden yazmayı deneyin. Derleyici görür, ön işleme sonra şekilde kodu görmek için kullanabileceğiniz [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) seçeneği.

Hatanın kaynağını yalıtmak ve bir iç derleyici hatası Microsoft'a hakkında daha fazla bilgi için bkz: [Visual C++ araç ile ilgili bir sorun bildirme](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md).