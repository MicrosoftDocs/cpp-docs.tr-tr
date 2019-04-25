---
title: BSCMAKE .Bsc Dosyasını Nasıl Derler
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6f721641e021396f112bfe4c075ca0f524100d1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291164"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE .Bsc Dosyasını Nasıl Derler

BSCMAKE oluşturur veya alabilir ve en verimli şekilde .bsc dosyası oluşturur. Olası sorunları önlemek için derleme işleminin anlaşılması önemlidir.

BSCMAKE gözatma bilgisi dosyası oluşturduğunda, uzunluğu sıfır .sbr dosyaları keser. Sıfır uzunluklu (veya boş) .sbr dosyası, aynı dosya sonraki derleme sırasında BSCMAKE .sbr dosyası yapmak için hiçbir yeni bir katkı olduğunu bildirir. Bu, BSCMAKE dosyasının bu bölümü, bir güncelleştirme gerekli değildir ve artımlı derleme yeterli olacaktır olanak tanır. Her derleme sırasında (/n seçeneği belirtilmediği sürece), BSCMAKE değişen .sbr dosyalarını kullanarak bir dosyayı artımlı olarak güncelleştirmek önce çalışır.

BSCMAKE .bsc dosyasını /o seçeneği ile belirtilen ada sahip arar. /O belirtilmezse, BSCMAKE .bsc uzantısı ile ilk .sbr dosyası ve temel adına sahip bir dosyasını arar. Dosya varsa, BSCMAKE katkıda bulunan .sbr dosyalarını kullanarak gözatma bilgisi dosyası, artımlı derleme gerçekleştirir. Dosya mevcut değilse, BSCMAKE tüm .sbr dosyalarını kullanarak tam bir derleme gerçekleştirir. Yapılar için kuralları aşağıdaki gibidir:

- Başarılı olması tam derleme için tüm .sbr dosyaları bulunmalı ve değil kesilmiş olarak belirtildi. .Sbr dosyası grafik kesilmişse, onu (yeniden derlemeden ya birleştirilmesini) BSCMAKE çalıştırmadan önce yeniden oluşturmanız gerekir.

- .Bsc dosyası başarılı olması Artımlı derleme için mevcut olması gerekir. Katkıda bulunan tüm .sbr dosyaları boş dosyalar bile bulunmalı ve BSCMAKE komut satırında belirtilmelidir. Komut satırından .sbr dosyası atlarsanız, BSCMAKE katkıyı dosyasından kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[.Bsc Dosyası Derleme](building-a-dot-bsc-file.md)
