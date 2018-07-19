---
title: '&lt;condition_variable&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <condition_variable>
dev_langs:
- C++
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7becd4cb5700cfb31acacc244d2640498bf8120e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963478"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

Sınıfları tanımlar [condition_variable](../standard-library/condition-variable-class.md) ve [condition_variable_any](../standard-library/condition-variable-any-class.md) bir koşul true olmasını bekleyin nesneleri oluşturmak için kullanılır.

Diğer ConcRT mekanizmaları ile birlikte kullanabilirsiniz, böylece bu başlığı eşzamanlılık çalışma zamanı (ConcRT) kullanır. ConcRT hakkında daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
#include <condition_variable>
```

> [!NOTE]
> Derlenmiş kodda **/CLR**, bu başlığı engellenir.

### <a name="remarks"></a>Açıklamalar

Bir koşul değişken aynı zamanda kullanmalıdır bekler kod bir `mutex`. Bir çağıran iş parçacığının kilitler gerekir `mutex` koşul değişkeni bekleyin işlevleri çağırmadan önce. `mutex` Çağrılan işlev döndürdüğünde ardından kilitlenir. `mutex` İş parçacığı koşul true olmasını beklerken kilitli değil. Böylece herhangi bir öngörülemeyen sonuçlara, için bir koşul değişken bekler her bir iş parçacığı aynı kullanmalısınız `mutex` nesne.

Türündeki nesneler `condition_variable_any` herhangi bir türde bir mutex ile kullanılabilir. Kullanılan mutex türünü sağlamak zorunda değildir `try_lock` yöntemi. Türündeki nesneler `condition_variable` ile türünde bir mutex kullanılması `unique_lock<mutex>`. Bu tür nesneler türündeki nesneler hızlı `condition_variable_any<unique_lock<mutex>>`.

Bir olay beklemek için önce mutex kilitleyebilir ve birini çağırın `wait` koşul değişkeni yöntemleri. `wait` Koşul değişkeni başka bir iş parçacığı verinceye kadar blokları çağırın.

*Sahte wakeups* bildirimleri olmadan koşul değişkenleri engeli için bekleyen iş parçacıklarının uygun oluşur. Kod bir bekleme işlevden döndükten sonra böyle alacaklardır wakeups tanımak için bir koşul true olmasını bekler kod açıkça bu koşulu denetlemeniz gerekir. Bu durum genellikle döngü kullanarak gerçekleştirilir; kullanabileceğiniz `wait(unique_lock<mutex>& lock, Predicate pred)` sizin için bu döngü gerçekleştirmek için.

```cpp
while (condition is false)
    wait for condition variable;
```

`condition_variable_any` Ve `condition_variable` sınıflarının her koşulunun oluşmasını bekler üç yöntem vardır.

- `wait` sınırsız bir süre boyunca bekler.

- `wait_until` Belirtilen kadar bekler `time`.

- `wait_for` Belirtilen bir bekler `time interval`.

Bu yöntemlerin her biri iki aşırı yüklenmiş sürümlerini içerir. Bir yalnızca bekler ve uyanabilir. Diğer bir koşulu tanımlayan bir ek şablon bağımsız değişkeni alır. Koşul olana kadar yöntemi döndürmüyor **true**.

Her sınıf kendi koşul olan bir koşul değişkenini bildirmek için kullanılan iki yöntem de sahiptir **true**.

- `notify_one` bir koşul değişken için bekleyen iş parçacıklarının uyku modundan çıkar.

- `notify_all` Koşul değişken için bekleyen iş parçacıklarının tüm uyku modundan çıkar.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[condition_variable Sınıfı](../standard-library/condition-variable-class.md)<br/>
[condition_variable_any Sınıfı](../standard-library/condition-variable-any-class.md)<br/>
