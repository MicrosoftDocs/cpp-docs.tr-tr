---
description: 'Daha fazla bilgi edinin: BSCMAKE bir oluşturur. BSC dosyası'
title: BSCMAKE .Bsc Dosyasını Nasıl Derler
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6d468f365f7f42be2eb393e53d72053b682ec65a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191387"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE .Bsc Dosyasını Nasıl Derler

BSCMAKE, en verimli şekilde bir. bsc dosyası oluşturur veya yeniden oluşturur. Olası sorunları önlemek için, yapı sürecini anlamak önemlidir.

BSCMAKE bir tarama bilgileri dosyası oluşturduğunda,. sbr dosyalarını sıfır uzunluğuna keser. Aynı dosyanın sonraki derlemesi sırasında sıfır uzunluğunda bir (veya boş). sbr dosyası BSCMAKE. sbr dosyasında oluşturulacak yeni bir katkı olmadığını söyler. BSCMAKE 'in, dosyanın söz konusu bölümünün bir güncelleştirmesinin gerekli olmadığını ve artımlı bir derlemeyi yeterli olacağını bilmesini sağlar. Her derleme sırasında (/n seçeneği belirtilmediği takdirde) BSCMAKE, yalnızca değişmiş olan. sbr dosyalarını kullanarak dosyayı artımlı olarak güncelleştirmeyi dener.

BSCMAKE,/o seçeneğiyle belirtilen adı taşıyan bir. bsc dosyası arar. /O belirtilmemişse BSCMAKE, ilk. sbr dosyasının ve. bsc uzantısının temel adına sahip bir dosya arar. Dosya varsa, BSCMAKE yalnızca katkıda bulunan. sbr dosyalarını kullanarak, tarama bilgileri dosyasının artımlı bir derlemesini gerçekleştirir. Dosya yoksa, BSCMAKE tüm. sbr dosyalarını kullanarak tam derleme gerçekleştirir. Derlemeler için kurallar aşağıdaki gibidir:

- Tam bir yapılandırmanın başarılı olması için, belirtilen tüm. sbr dosyalarının mevcut olması ve kesilmemelidir. Bir. sbr dosyası kesilmişse, BSCMAKE 'i çalıştırmadan önce yeniden oluşturmanız gerekir (yeniden derleyerek veya montaj aracılığıyla).

- Artımlı bir yapılandırmanın başarılı olması için. bsc dosyası var olmalıdır. Tüm katkıda bulunan. sbr dosyaları, hatta boş dosyalar var olmalıdır ve BSCMAKE komut satırında belirtilmelidir. Komut satırından bir. sbr dosyasını atlarsanız, BSCMAKE dosyanın katkısını kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Oluşturma. BSC dosyası](building-a-dot-bsc-file.md)
