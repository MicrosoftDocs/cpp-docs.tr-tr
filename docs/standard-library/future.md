---
title: '&lt;yayımlanacak&gt;'
ms.date: 11/04/2016
f1_keywords:
- <future>
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
ms.openlocfilehash: b5f18de772ea2221ecbd4098b94e0b4f14c0484c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220931"
---
# <a name="ltfuturegt"></a>&lt;yayımlanacak&gt;

\<future>Sınıf şablonları tanımlamak için standart üstbilgiyi ve bir işlevi çalıştırmayı kolaylaştıran bir işlev (muhtemelen ayrı bir iş parçacığında) ve sonucunu almak için destekleme şablonlarını dahil edin. Sonuç, işlev tarafından döndürülen değer ya da işlev tarafından yayılan ancak işlevde yakalanmayan bir özel durumdur.

Bu üst bilgi, diğer ConcRT mekanizmalarıyla birlikte kullanabilmeniz için Eşzamanlılık Çalışma Zamanı (ConcRT) kullanır. ConcRT hakkında daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
#include <future>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

*Zaman uyumsuz bir sağlayıcı* , bir işlev çağrısının sonucunu depolar. Bir işlev çağrısının sonucunu almak için *zaman uyumsuz bir dönüş nesnesi* kullanılır. *İlişkili bir zaman uyumsuz durum* , zaman uyumsuz bir sağlayıcı ile bir veya daha fazla zaman uyumsuz dönüş nesnesi arasında iletişim sağlar

Bir program, ilişkili zaman uyumsuz durum nesnelerini doğrudan oluşturmaz. Program, her ihtiyaç duyduğunda bir zaman uyumsuz sağlayıcı oluşturur ve bundan sonra ilişkili zaman uyumsuz durumunu sağlayıcıyla paylaşan bir zaman uyumsuz dönüş nesnesi oluşturur. Zaman uyumsuz sağlayıcılar ve zaman uyumsuz döndürme nesneleri, paylaşılan ilişkili zaman uyumsuz durumlarını tutan nesneleri yönetir. İlişkili zaman uyumsuz duruma başvuran son nesne onu serbest bıraktığında, ilişkili zaman uyumsuz durumu tutan nesne yok edilir.

Zaman uyumsuz bir sağlayıcı veya ilişkili zaman uyumsuz durumu olmayan bir zaman uyumsuz dönüş nesnesi *boş*.

İlişkili bir zaman uyumsuz durum *, yalnızca zaman* uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

Şablon işlevi `async` ve sınıf şablonları `promise` ve `packaged_task` zaman uyumsuz sağlayıcılardır. Sınıf şablonları `future` ve `shared_future` zaman uyumsuz dönüş nesnelerini açıkla.

, Ve sınıf şablonlarının her biri, `promise` `future` `shared_future` türü için bir özelleşmeye ve bir **`void`** değeri başvuruya göre depolamaya ve almaya yönelik kısmi bir özelleşmeye sahiptir. Bu uzmanlıklar, birincil şablondan yalnızca, döndürülen değeri depolayan ve alan işlevlerin imzalarındaki ve semantiklerinden farklıdır.

`future` `shared_future` Geri uyumluluk için korunmakta olan bir durum dışında, sınıf şablonları ve yıkıcılarının hiçbir yerde engellenmemesi: ile başlatılan bir göreve eklenen diğer tüm vadeli sürelerden farklı olarak, `future` `shared_future` `std::async` yok edicisi, görev tamamlanmadıysa, yıkıcı engeller; diğer bir deyişle, bu iş parçacığının henüz çağrı gerçekleştirmediyse `.get()` veya `.wait()` görev hala çalışmaya devam ediyorsa engeller. Aşağıdaki kullanılabilirlik notunun açıklaması `std::async` taslak standardında eklenmiştir: "[dikkat: std:: Async öğesinden daha sonra elde edilen bir işlem yerel kapsam dışına taşınırsa, ileride bunu kullanan diğer kod, gelecekteki yok edicinin, paylaşılan durumun kullanılabilir hale gelmesini engelleyebileceğini unutmayın. — Note]" diğer tüm durumlarda, yok `future` `shared_future` ediciler gereklidir ve hiçbir zaman engellenmemelidir.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[gelecek sınıf](../standard-library/future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar.|
|[future_error sınıfı](../standard-library/future-error-class.md)|Nesneleri yöneten türdeki yöntemlerle oluşturulabilecek bir özel durum nesnesi tanımlar `future` .|
|[packaged_task sınıfı](../standard-library/packaged-task-class.md)|Çağrı sarmalayıcısı olan ve çağrı imzası olan zaman uyumsuz sağlayıcıyı açıklar `Ty(ArgTypes...)` . İlişkili zaman uyumsuz durumu, olası sonucun yanı sıra çağrılabilir nesnesinin bir kopyasını tutar.|
|[Promise sınıfı](../standard-library/promise-class.md)|Zaman uyumsuz sağlayıcıyı açıklar.|
|[shared_future sınıfı](../standard-library/shared-future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar. Bir `future` nesnenin aksine, zaman uyumsuz bir sağlayıcı herhangi bir sayıda `shared_future` nesneyle ilişkilendirilebilir.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[is_error_code_enum Yapısı](../standard-library/is-error-code-enum-structure.md)|Öğesinin depolanması için uygun olduğunu gösteren özelleşme `future_errc` `error_code` .|
|[uses_allocator Yapısı](../standard-library/uses-allocator-structure.md)|Her zaman true tutan özelleştirme.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[async](../standard-library/future-functions.md#async)|Zaman uyumsuz sağlayıcıyı temsil eder.|
|[future_category](../standard-library/future-functions.md#future_category)|`error_category`Nesneler ile ilişkili hataları karakterlendirir nesnesine bir başvuru döndürür `future` .|
|[make_error_code](../standard-library/future-functions.md#make_error_code)|`error_code` `error_category` Hataları karakterleştiren nesnesine sahip bir oluşturur `future` .|
|[make_error_condition](../standard-library/future-functions.md#make_error_condition)|`error_condition` `error_category` Hataları karakterleştiren nesnesine sahip bir oluşturur `future` .|
|[Kur](../standard-library/future-functions.md#swap)|Bir nesnenin ilişkili zaman uyumsuz durumunu `promise` başka bir nesneyle değiş tokuş eder.|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[future_errc](../standard-library/future-enums.md#future_errc)|Sınıfı tarafından bildirilen hatalar için simgesel adlar sağlar `future_error` .|
|[future_status](../standard-library/future-enums.md#future_status)|, Zaman aşımına uğramayı bekleyen bir işlevin döndürebileceği nedenlerle sembolik adlar sağlar.|
|[Man](../standard-library/future-enums.md#launch)|Şablon işlevi için olası modları açıklayan bir bit maskesi türünü temsil eder `async` .|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
