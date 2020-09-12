---
title: high_resolution_clock struct | Microsoft Docs
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
ms.openlocfilehash: 341cae04742d72fdcc7483e74977bf413854df82
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039657"
---
# <a name="high_resolution_clock-struct"></a>high_resolution_clock yapısı

Bir *high_resolution* saati temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class high_resolution_clock
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`duration`|İçin bir eş anlamlı `nanoseconds` , içinde tanımlanır \<chrono> .|
|`period`|İçin bir eş anlamlı `nano` , içinde tanımlanır \<ratio> .|
|`rep`|İçin bir eş anlamlı **`long long`** , öğesinin içerilen örneklemede saat işaretleri sayısını temsil etmek için kullanılan tür `duration` .|
|`time_point`|İçin bir eş anlamlı `chrono::time_point<high_resolution_clock>` .|

## <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|`now`|Geçerli saati bir değer olarak döndürür `time_point` .|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|`is_steady`|Tutar **`true`** . Bir `high_resolution_clock` *sabit*değer.|
