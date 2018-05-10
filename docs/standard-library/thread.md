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
ms.openlocfilehash: 5558f1e7998cca1efd64fbc5ee0ad39cc40ee2a6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

Standart üstbilgisini \<iş parçacığı > sınıfı tanımlamak için `thread` ve çeşitli destekleyici işlevler.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <thread>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.

`__STDCPP_THREADS__` Makrosu iş parçacıklarını bu üstbilgisi tarafından desteklendiğini belirtmek için sıfır olmayan bir değer olarak tanımlanır.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[thread Sınıfı](../standard-library/thread-class.md)|İnceleyin ve bir iş parçacığı bir uygulamada yürütme yönetmek için kullanılan nesneyi tanımlar.|

### <a name="public-structures"></a>Genel yapılar

|Ad|Açıklama|
|----------|-----------------|
|[hash Yapısı (C++ Standart Kitaplığı)](../standard-library/hash-structure-stl.md)|Benzersiz olarak tarafından belirlenen bir değer döndüren bir üye işlevi tanımlayan bir `thread::id`. Üye işlevini tanımlayan bir [karma](../standard-library/hash-class.md) eşleme türü değerleri için uygun işlevi `thread::id` dizin değerlerin bir dağıtım.|

### <a name="public-functions"></a>Genel işlevler

|Ad|Açıklama|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|Geçerli yürütme iş parçacığı benzersiz olarak tanımlar.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Çağıran iş parçacığı engeller.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Çağıran iş parçacığı en az belirtilen zamana kadar engeller.|
|[Değiştirme](../standard-library/thread-functions.md#swap)|İki durumlarını alış verişleri `thread` nesneleri.|
|[yield](../standard-library/thread-functions.md#yield)|Geçerli iş parçacığının normal şekilde çalışmaya devam eder olsa bile diğer iş parçacıklarını çalıştırmak için işletim sistemi işaret eder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator > = işleci](../standard-library/thread-operators.md#op_gt_eq)|Bir olup olmadığını belirleyen `thread::id` nesnesidir başka eşit veya daha büyük.|
|[operator > işleci](../standard-library/thread-operators.md#op_gt)|Bir olup olmadığını belirleyen `thread::id` nesnesidir diğerinden daha büyük.|
|[operator < = işleci](../standard-library/thread-operators.md#op_lt_eq)|Bir olup olmadığını belirleyen `thread::id` nesnesidir değerinden küçük veya eşit başka.|
|[operator < işleci](../standard-library/thread-operators.md#op_lt)|Bir olup olmadığını belirleyen `thread::id` nesnesi, başka değerinden.|
|[operator! = işleci](../standard-library/thread-operators.md#op_neq)|İki karşılaştırır `thread::id` eşitsizlik nesneleri.|
|[operator == işleci](../standard-library/thread-operators.md#op_eq_eq)|İki karşılaştırır `thread::id` nesneleri eşitlik için.|
|[işleç << işleci](../standard-library/thread-operators.md#op_lt_lt)|Bir metin gösterimini ekler bir `thread::id` bir akış nesnesine.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
