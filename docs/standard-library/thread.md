---
title: '&lt;iş parçacığı&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef5470d7c7e83c260f44d723665d5d9c0a5ad061
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953035"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

Standart üst bilgiyi dahil \<iş parçacığı > sınıfını tanımlamak için **iş parçacığı** ve çeşitli destekleyici işlevler.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <thread>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Derlenmiş kodda **/CLR**, bu başlığı engellenir.

`__STDCPP_THREADS__` Makrosu, iş parçacıkları bu üstbilgisi tarafından desteklendiğini belirten sıfır olmayan bir değer olarak tanımlanır.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[thread Sınıfı](../standard-library/thread-class.md)|İnceleyin ve bir iş parçacığı, bir uygulamada yönetmek için kullanılan nesneyi tanımlar.|

### <a name="public-structures"></a>Genel yapılar

|Ad|Açıklama|
|----------|-----------------|
|[hash Yapısı (C++ Standart Kitaplığı)](../standard-library/hash-structure-stl.md)|Benzersiz tarafından belirlenen bir değer döndüren bir üye işlev tanımlayan bir `thread::id`. Üye işlevini tanımlayan bir [karma](../standard-library/hash-class.md) eşleme türü değerleri için uygun işlevi `thread::id` dizin değerlerinin dağıtımına.|

### <a name="public-functions"></a>Genel işlevleri

|Ad|Açıklama|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|Geçerli iş parçacığı yürütme benzersiz olarak tanımlar.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Çağıran iş parçacığını engeller.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Çağıran iş parçacığını en az belirtilen süre kadar engeller.|
|[değiştirme](../standard-library/thread-functions.md#swap)|İki durumlarını birbiriyle değiştirir **iş parçacığı** nesneleri.|
|[yield](../standard-library/thread-functions.md#yield)|Geçerli iş parçacığını normal şekilde çalışmaya devam ediyordu olsa bile işletim sisteminin diğer iş parçacıklarını çalıştırmasını bildirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator > = işleci](../standard-library/thread-operators.md#op_gt_eq)|Az olup olmadığını belirler `thread::id` büyüktür veya eşittir başka bir nesne.|
|[operator > işleci](../standard-library/thread-operators.md#op_gt)|Az olup olmadığını belirler `thread::id` nesnedir diğerinden daha büyük.|
|[operator < = işleci](../standard-library/thread-operators.md#op_lt_eq)|Az olup olmadığını belirler `thread::id` küçüktür veya eşittir başka bir nesne değil.|
|[operator < işleci](../standard-library/thread-operators.md#op_lt)|Az olup olmadığını belirler `thread::id` başka bir nesne değil.|
|[işleç! = işleci](../standard-library/thread-operators.md#op_neq)|İki karşılaştırır `thread::id` nesneleri için eşitsizlik.|
|[operator == işleci](../standard-library/thread-operators.md#op_eq_eq)|İki karşılaştırır `thread::id` eşitlik için nesneleri.|
|[işleç << işleci](../standard-library/thread-operators.md#op_lt_lt)|Bir metin temsilini ekler bir `thread::id` bir akış nesnesine.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
