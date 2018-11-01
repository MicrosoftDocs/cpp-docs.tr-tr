---
title: NMAKE Çıkış Kodları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 08aceadf107112b446844b09fad24a11fbe7a731
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499599"
---
# <a name="exit-codes-from-nmake"></a>NMAKE Çıkış Kodları

NMAKE aşağıdaki çıkış kodlarını döndürür:

|Kod|Açıklama|
|----------|-------------|
|0|Hata (büyük olasılıkla bir uyarı)|
|1.|Eksik yapı (yalnızca /K kullanıldığında verilen)|
|2|Program hata, nedeni aşağıdakilerden biri:|
||-Derleme görevleri dosyası bir sözdizimi hatası|
||-Komutundan bir hata veya çıkış kodu|
||Kullanıcı tarafından kesinti|
|4|Sistem hatası: bellek yetersiz|
|255|Hedef (yalnızca /Q kullanıldığında verilen) güncel değil|

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Çalıştırma](../build/running-nmake.md)