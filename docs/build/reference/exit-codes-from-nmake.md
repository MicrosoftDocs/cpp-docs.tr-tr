---
title: NMAKE Çıkış Kodları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 25ea4060e7b7a968b6a9da78f344e645c5d43a44
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823504"
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

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Çalıştırma](running-nmake.md)
