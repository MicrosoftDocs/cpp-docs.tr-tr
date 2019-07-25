---
title: '&lt;thread&gt;'
ms.date: 11/04/2016
f1_keywords:
- <thread>
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
ms.openlocfilehash: 7053402dfb566f10c7be4c0eebaef40f3d371f43
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460080"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

Sınıf **iş parçacığını** ve \<çeşitli destekleyici işlevleri tanımlamak için > Standart üst bilgi iş parçacığını ekleyin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <thread>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

`__STDCPP_THREADS__` Makro, iş parçacıklarının bu üst bilgi tarafından desteklendiğini göstermek için sıfır dışında bir değer olarak tanımlanır.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Ortak sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[thread Sınıfı](../standard-library/thread-class.md)|Bir uygulamadaki yürütmenin iş parçacığını gözlemlemek ve yönetmek için kullanılan bir nesneyi tanımlar.|

### <a name="public-structures"></a>Ortak yapılar

|Ad|Açıklama|
|----------|-----------------|
|[hash Yapısı (C++ Standart Kitaplığı)](../standard-library/hash-structure-stl.md)|Tarafından benzersiz olarak belirlenen bir değer döndüren bir üye işlevi tanımlar `thread::id`. Üye işlevi, türündeki `thread::id` değerleri dizin değerlerinin bir dağıtımına eşlemek için uygun bir [karma](../standard-library/hash-class.md) işlevi tanımlar.|

### <a name="public-functions"></a>Ortak Işlevler

|Ad|Açıklama|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|Yürütmenin geçerli iş parçacığını benzersiz şekilde tanımlar.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Çağıran iş parçacığını engeller.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Çağıran iş parçacığını, belirtilen saate kadar en az kadar engeller.|
|[Kur](../standard-library/thread-functions.md#swap)|İki **iş parçacığı** nesnesinin durumlarını değiş tokuş eder.|
|[yield](../standard-library/thread-functions.md#yield)|Geçerli iş parçacığı normalde çalışmaya devam edebilse bile, işletim sistemine diğer iş parçacıklarını çalıştırmasını bildirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator > = Işleci](../standard-library/thread-operators.md#op_gt_eq)|Bir `thread::id` nesnenin diğerinden büyük veya ona eşit olup olmadığını belirler.|
|[işleç > Işleci](../standard-library/thread-operators.md#op_gt)|Bir `thread::id` nesnenin diğerinden daha büyük olup olmadığını belirler.|
|[operator < = Işleci](../standard-library/thread-operators.md#op_lt_eq)|Bir `thread::id` nesnenin diğerine eşit veya ondan küçük olup olmadığını belirler.|
|[işleç < Işleci](../standard-library/thread-operators.md#op_lt)|Bir `thread::id` nesnenin diğerinden daha küçük olup olmadığını belirler.|
|[operator! = Işleci](../standard-library/thread-operators.md#op_neq)|Eşitsizlik için `thread::id` iki nesneyi karşılaştırır.|
|[operator = = Işleci](../standard-library/thread-operators.md#op_eq_eq)|, Eşitlik `thread::id` için iki nesneyi karşılaştırır.|
|[işleç < < Işleci](../standard-library/thread-operators.md#op_lt_lt)|Bir `thread::id` nesnenin bir akışa metin temsilini ekler.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
