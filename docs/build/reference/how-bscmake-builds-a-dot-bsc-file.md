---
title: BSCMAKE .Bsc Dosyasını Nasıl Derler
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 053bc7565accce5db8998ae8efec256ef37d37b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442594"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE .Bsc Dosyasını Nasıl Derler

BSCMAKE oluşturur veya alabilir ve en verimli şekilde .bsc dosyası oluşturur. Olası sorunları önlemek için derleme işleminin anlaşılması önemlidir.

BSCMAKE gözatma bilgisi dosyası oluşturduğunda, uzunluğu sıfır .sbr dosyaları keser. Sıfır uzunluklu (veya boş) .sbr dosyası, aynı dosya sonraki derleme sırasında BSCMAKE .sbr dosyası yapmak için hiçbir yeni bir katkı olduğunu bildirir. Bu, BSCMAKE dosyasının bu bölümü, bir güncelleştirme gerekli değildir ve artımlı derleme yeterli olacaktır olanak tanır. Her derleme sırasında (/n seçeneği belirtilmediği sürece), BSCMAKE değişen .sbr dosyalarını kullanarak bir dosyayı artımlı olarak güncelleştirmek önce çalışır.

BSCMAKE .bsc dosyasını /o seçeneği ile belirtilen ada sahip arar. /O belirtilmezse, BSCMAKE .bsc uzantısı ile ilk .sbr dosyası ve temel adına sahip bir dosyasını arar. Dosya varsa, BSCMAKE katkıda bulunan .sbr dosyalarını kullanarak gözatma bilgisi dosyası, artımlı derleme gerçekleştirir. Dosya mevcut değilse, BSCMAKE tüm .sbr dosyalarını kullanarak tam bir derleme gerçekleştirir. Yapılar için kuralları aşağıdaki gibidir:

- Başarılı olması tam derleme için tüm .sbr dosyaları bulunmalı ve değil kesilmiş olarak belirtildi. .Sbr dosyası grafik kesilmişse, onu (yeniden derlemeden ya birleştirilmesini) BSCMAKE çalıştırmadan önce yeniden oluşturmanız gerekir.

- .Bsc dosyası başarılı olması Artımlı derleme için mevcut olması gerekir. Katkıda bulunan tüm .sbr dosyaları boş dosyalar bile bulunmalı ve BSCMAKE komut satırında belirtilmelidir. Komut satırından .sbr dosyası atlarsanız, BSCMAKE katkıyı dosyasından kaldırır.

## <a name="see-also"></a>Ayrıca Bkz.

[.Bsc Dosyası Derleme](../../build/reference/building-a-dot-bsc-file.md)