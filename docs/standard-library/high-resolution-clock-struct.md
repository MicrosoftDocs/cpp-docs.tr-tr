---
title: high_resolution_clock yapı | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b00b20e7cea4fa24b37ad33d5536eb9844e6953
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268092"
---
# <a name="steadyclock-struct"></a>steady_clock yapısı

Temsil eden bir *high_resolution* saati.

## <a name="syntax"></a>Sözdizimi

```cpp
class high_resolution_clock
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`duration`|İçin bir eşanlamlı `nanoseconds`içinde tanımlanmış \<chrono >.|
|`period`|İçin bir eşanlamlı `nano`içinde tanımlanmış \<oranı >.|
|`rep`|İçin bir eşanlamlı **uzun** **uzun**, içinde içerilen saat tik taklarının sayısını belirtmek için kullanılan tür `duration`.|
|`time_point`|İçin bir eşanlamlı `chrono::time_point<high_resolution_clock>`.|

## <a name="functions"></a>İşlevler

|||
|-|-|
|`now`|Olarak geçerli saati döndürür bir `time_point` değeri.|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|`is_steady`|Tutan **true**. A `high_resolution_clock` olduğu *sürekli*.|
