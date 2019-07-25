---
title: '&lt;condition_variable&gt;'
ms.date: 11/04/2016
f1_keywords:
- <condition_variable>
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
ms.openlocfilehash: e63dc5a494f471997c28be8b2cd237aba45a6fd6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457391"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

Bir koşulun doğru olmasını bekleyen nesneler oluşturmak için kullanılan [condition_variable](../standard-library/condition-variable-class.md) ve [condition_variable_any](../standard-library/condition-variable-any-class.md) sınıflarını tanımlar.

Bu üst bilgi, diğer ConcRT mekanizmalarıyla birlikte kullanabilmeniz için Eşzamanlılık Çalışma Zamanı (ConcRT) kullanır. ConcRT hakkında daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<condition_variable >

**Ad alanı:** std

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

### <a name="remarks"></a>Açıklamalar

Bir koşul değişkeni için bekleyen kodun de bir `mutex`kullanması gerekir. Çağıran iş parçacığı, `mutex` koşul değişkeni için bekleyen işlevleri çağırmadan önce öğesini kilitlemelidir. `mutex` Çağrılan işlev döndürüldüğünde kilitlenir. `mutex` İş parçacığı koşulun doğru olmasını beklediği sürece kilitli değildir. Öngörülemeyen sonuçlar bulunmadığından, bir koşul değişkeni için bekleyen her iş parçacığının aynı `mutex` nesneyi kullanması gerekir.

Türündeki `condition_variable_any` nesneler, her türlü bir mutex ile kullanılabilir. Kullanılan mutex türünün `try_lock` yöntemi sağlaması gerekmez. Türündeki `condition_variable` nesneler yalnızca, türünde `unique_lock<mutex>`bir mutex ile kullanılabilir. Bu türden nesneler, türündeki `condition_variable_any<unique_lock<mutex>>`nesnelerden daha hızlı olabilir.

Bir olayı beklemek için, önce mutex 'i kilitleyin ve sonra koşul değişkeninde `wait` yöntemlerden birini çağırın. `wait` Çağrı, başka bir iş parçacığı koşul değişkenine işaret edene kadar engeller.

Durum değişkenlerini bekleyen iş parçacıkları uygun bildirimler olmadan engellenmemiş hale geldiğinde *Spuremwakeups* oluşur. Bu tür spuremwakeups 'ı tanımak için, bir koşulun true hale gelmesini bekleyen kod, kod bir bekleme işlevinden döndürüldüğünde bu koşulu açıkça denetlemelidir. Bu genellikle bir döngü kullanılarak yapılır; Bu döngüyü sizin `wait(unique_lock<mutex>& lock, Predicate pred)` için yapmak üzere kullanabilirsiniz.

```cpp
while (condition is false)
    wait for condition variable;
```

`condition_variable_any` Ve`condition_variable` sınıflarının her biri, bir koşulu bekleyen üç yönteme sahiptir.

- `wait`Sınırlandırılmamış bir zaman aralığı bekler.

- `wait_until`Belirtilen `time`bir olana kadar bekler.

- `wait_for`Belirtilen `time interval`bir için bekler.

Bu yöntemlerin her birinin iki aşırı yüklü sürümü vardır. Yalnızca bir bekler ve uyanabilir uyandırabilirler. Diğeri, bir koşulu tanımlayan ek bir şablon bağımsız değişkeni alır. Yöntemi, koşul **true**olana kadar döndürmez.

Her sınıfta, koşulunun **doğru**olduğunu bildiren bir koşul değişkenine bildirimde bulunan iki yöntem de vardır.

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
[condition_variable_any Sınıfı](../standard-library/condition-variable-any-class.md)
