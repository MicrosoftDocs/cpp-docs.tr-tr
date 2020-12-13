---
description: Giriş ve çıkış hakkında daha fazla bilgi edinin
title: Girdi ve Çıktı
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
ms.openlocfilehash: 0edd66765f1633dc0adf12b311faf81d3a030512
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334283"
---
# <a name="input-and-output"></a>Girdi ve Çıktı

G/ç işlevleri, dosyalara ve cihazlara veri okur ve bunları yazar. Dosya g/ç işlemleri metin modunda veya ikili modda gerçekleşirken. Microsoft çalışma zamanı kitaplığı 'nın üç tür g/ç işlevi vardır:

- [Stream g/ç](../c-runtime-library/stream-i-o.md) işlevleri verileri ayrı karakterlerin akışı olarak değerlendirir.

- Alt düzey [g/ç](../c-runtime-library/low-level-i-o.md) işlevleri, akış g/ç tarafından sağlananından daha düşük düzeydeki işlem için işletim sistemini doğrudan çağırır.

- [Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md) işlevleri doğrudan bir konsola (klavye ve ekran) veya g/ç bağlantı noktasına (yazıcı bağlantı noktası gibi) okur veya yazar.

   > [!NOTE]
   > Stream işlevleri arabelleğe alındığından ve alt düzey işlevler olmadığından, bu iki tür işlev genellikle uyumsuzdur. Belirli bir dosyayı işlemek için, yalnızca Stream veya alt düzey işlevleri kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
