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
ms.openlocfilehash: 850d5e3a5434aa44e23a7f74aeb9c306ab6c0a8e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203214"
---
# <a name="steady_clock-struct"></a>steady_clock yapısı

Bir *high_resolution* saati temsil eder.

## <a name="syntax"></a>Sözdizimi

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

|||
|-|-|
|`now`|Geçerli saati bir değer olarak döndürür `time_point` .|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|`is_steady`|Tutar **`true`** . Bir `high_resolution_clock` *sabit*değer.|
