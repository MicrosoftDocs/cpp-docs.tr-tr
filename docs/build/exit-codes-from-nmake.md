---
title: NMAKE çıkış kodları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b5a593e38efb5230630ed01e65f4bfb1f2ba92a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722624"
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