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
ms.openlocfilehash: a54045dfdebf3ab7c9f7ad04611bc9e267faea0d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845732"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

Sınıflarını tanımlayan [condition_variable](../standard-library/condition-variable-class.md) ve [condition_variable_any](../standard-library/condition-variable-any-class.md) bir koşul doğru olmasını bekleyin nesneleri oluşturmak için kullanılır.

Bu üst eşzamanlılık çalışma zamanı (ConcRT) kullanır, böylece diğer ConcRT mekanizmaları ile birlikte kullanabilirsiniz. ConcRT hakkında daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
#include <condition_variable>
```

> [!NOTE]
> Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.

### <a name="remarks"></a>Açıklamalar

Bir koşul değişkeni de kullanmalıdır bekler kodu bir `mutex`. Çağıran iş parçacığı kilitlemek gerekir `mutex` koşul değişkeni bekleyin işlevleri çağırmadan önce. `mutex` Çağrılan işlev döndürdüğünde ardından kilitlenir. `mutex` İş parçacığı koşul doğru olmasını beklerken kilitli değil. Vardır; böylece hiçbir öngörülemeyen sonuçlara, için bir koşul değişkeni bekler her bir iş parçacığı aynı kullanmalısınız `mutex` nesnesi.

Nesne türü `condition_variable_any` herhangi bir türde bir mutex kullanılabilir. Sağlamak kullanılan mutex türü yok `try_lock` yöntemi. Nesne türü `condition_variable` türünde bir mutex yalnızca kullanılabilir `unique_lock<mutex>`. Bu tür nesneler türündeki nesneleri hızlı `condition_variable_any<unique_lock<mutex>>`.

Bir olayı bekle için önce mutex kilitlemek ve aşağıdakilerden birini çağırın `wait` koşul değişkeni yöntemleri. `wait` Koşul değişkeni başka bir iş parçacığı verinceye kadar blokları çağırın.

*Alacaklardır wakeups* koşul değişkenleri olmadan engeli hale için bekleyen iş parçacığı bildirimleri uygun oluşur. Kod bir bekleme işlevi döndüğünde böyle alacaklardır wakeups tanımak için bir koşul doğru olmasını bekler kod açıkça bu koşulu denetlemeniz gerekir. Bu genellikle bir döngü kullanarak gerçekleştirilir; kullanabileceğiniz `wait(unique_lock<mutex>& lock, Predicate pred)` sizin için bu döngü gerçekleştirmek için.

```cpp
while (condition is false)
    wait for condition variable;
```

`condition_variable_any` Ve `condition_variable` sınıflarının her bekleme koşulu için üç yöntem vardır.

- `wait` sınırsız bir süre için bekler.

- `wait_until` Belirtilen bir kadar bekler `time`.

- `wait_for` Belirtilen bir bekler `time interval`.

Bu yöntemlerin her biri iki aşırı yüklenmiş sürümlerini içerir. Yalnızca bekler ve spuriously uyandırmak. Diğer bir koşulu tanımlayan ek şablon bağımsız değişken alır. Koşul kadar yöntemi döndürmüyor `true`.

Her sınıf kendi koşulu olan bir koşul değişken bildirmek için kullanılan iki yöntem de sahiptir `true`.

- `notify_one` bir koşul değişken için bekleyen iş parçacıklarının uyandırır.

- `notify_all` Koşul değişken için bekleyen iş parçacıklarının tümünü uyandırır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[condition_variable Sınıfı](../standard-library/condition-variable-class.md)<br/>
[condition_variable_any Sınıfı](../standard-library/condition-variable-any-class.md)<br/>
