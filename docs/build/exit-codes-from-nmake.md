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
ms.openlocfilehash: 1c70c76292b62560b1d9895aca2851b4cf56802b
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861804"
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