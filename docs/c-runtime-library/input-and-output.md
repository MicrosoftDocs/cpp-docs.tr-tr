---
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
ms.openlocfilehash: 2669ed3437fe0eea7dd648367feabe66ae6ed6d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62343192"
---
# <a name="input-and-output"></a>Girdi ve Çıktı

G/ç işlevleri okuyup veri için dosyaları ve cihazlardan yazma. Dosya g/ç işlemleri metin modunda veya İkili modda gerçekleşir. Microsoft çalışma zamanı kitaplığının g/ç işlevleri üç tür vardır:

- [Stream g/ç](../c-runtime-library/stream-i-o.md) işlevleri veri karakterlerin tek tek bir akış olarak değerlendir.

- [Düşük düzey g/ç](../c-runtime-library/low-level-i-o.md) işlevleri çağırma doğrudan akış g/ç tarafından sağlanan daha düşük düzeyli işlem için işletim sistemi.

- [Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md) işlevleri okuma veya doğrudan bir konsol (klavye ve ekran) veya bir g/ç bağlantı noktası (örneğin, yazıcı bağlantı noktasını) yazın.

   > [!NOTE]
   > Bu iki tür işlev, genellikle akışı işlevleri arabelleğe ve düşük düzeyli işlevleri değildir çünkü uyumsuzdur. Belirli bir dosya işlenmeden için akış ya da düşük düzeyli işlevleri özel olarak kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
