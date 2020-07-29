---
title: '&lt;condition_variable&gt;'
ms.date: 11/04/2016
f1_keywords:
- <condition_variable>
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
ms.openlocfilehash: d13b58fc05055ceecb6472003d7682c41c76e23d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222543"
---
# <a name="ltcondition_variablegt"></a>&lt;condition_variable&gt;

Bir koşulun doğru olmasını bekleyen nesneler oluşturmak için kullanılan [condition_variable](../standard-library/condition-variable-class.md) ve [condition_variable_any](../standard-library/condition-variable-any-class.md) sınıflarını tanımlar.

Bu üst bilgi, diğer ConcRT mekanizmalarıyla birlikte kullanabilmeniz için Eşzamanlılık Çalışma Zamanı (ConcRT) kullanır. ConcRT hakkında daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<condition_variable>

**Ad alanı:** std

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

### <a name="remarks"></a>Açıklamalar

Bir koşul değişkeni için bekleyen kodun de bir kullanması gerekir `mutex` . Çağıran iş parçacığı, `mutex` koşul değişkeni için bekleyen işlevleri çağırmadan önce öğesini kilitlemelidir. `mutex`Çağrılan işlev döndürüldüğünde kilitlenir. `mutex`İş parçacığı koşulun doğru olmasını beklediği sürece kilitli değildir. Öngörülemeyen sonuçlar bulunmadığından, bir koşul değişkeni için bekleyen her iş parçacığının aynı nesneyi kullanması gerekir `mutex` .

Türündeki nesneler `condition_variable_any` , her türlü bir mutex ile kullanılabilir. Kullanılan mutex türünün yöntemi sağlaması gerekmez `try_lock` . Türündeki nesneler `condition_variable` yalnızca, türünde bir mutex ile kullanılabilir `unique_lock<mutex>` . Bu türden nesneler, türündeki nesnelerden daha hızlı olabilir `condition_variable_any<unique_lock<mutex>>` .

Bir olayı beklemek için, önce mutex 'i kilitleyin ve sonra `wait` koşul değişkeninde yöntemlerden birini çağırın. `wait`Çağrı, başka bir iş parçacığı koşul değişkenine işaret edene kadar engeller.

Durum değişkenlerini bekleyen iş parçacıkları uygun bildirimler olmadan engellenmemiş hale geldiğinde *Spuremwakeups* oluşur. Bu tür spuremwakeups 'ı tanımak için, bir koşulun true hale gelmesini bekleyen kod, kod bir bekleme işlevinden döndürüldüğünde bu koşulu açıkça denetlemelidir. Bu genellikle bir döngü kullanılarak yapılır; `wait(unique_lock<mutex>& lock, Predicate pred)`Bu döngüyü sizin için yapmak üzere kullanabilirsiniz.

```cpp
while (condition is false)
    wait for condition variable;
```

`condition_variable_any`Ve `condition_variable` sınıflarının her biri, bir koşulu bekleyen üç yönteme sahiptir.

- `wait`Sınırlandırılmamış bir zaman aralığı bekler.

- `wait_until`Belirtilen bir olana kadar bekler `time` .

- `wait_for`Belirtilen bir için bekler `time interval` .

Bu yöntemlerin her birinin iki aşırı yüklü sürümü vardır. Yalnızca bir bekler ve uyanabilir uyandırabilirler. Diğeri, bir koşulu tanımlayan ek bir şablon bağımsız değişkeni alır. Yöntemi, koşul olana kadar döndürmez **`true`** .

Her sınıfta, koşulunun olduğu bir koşul değişkenine bildirimde bulunan iki yöntem de vardır **`true`** .

- `notify_one`koşul değişkeni için bekleyen iş parçacıklarından birini uyandırır.

- `notify_all`koşul değişkeni için bekleyen tüm iş parçacıklarını uyandırır.

## <a name="functions-and-enums"></a>İşlevler ve numaralandırmalar

```cpp
void notify_all_at_thread_exit(condition_variable& cond, unique_lock<mutex> lk);

enum class cv_status { no_timeout, timeout };
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[condition_variable sınıfı](../standard-library/condition-variable-class.md)\
[condition_variable_any sınıfı](../standard-library/condition-variable-any-class.md)
