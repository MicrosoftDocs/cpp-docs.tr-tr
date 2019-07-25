---
title: '&lt;yayımlanacak&gt;'
ms.date: 11/04/2016
f1_keywords:
- <future>
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
ms.openlocfilehash: d33b67ed17a95b6717878aaca2f61682b1807c15
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454001"
---
# <a name="ltfuturegt"></a>&lt;yayımlanacak&gt;

Bir işlevi çalıştırmayı kolaylaştıran \<şablon sınıflarını ve destekleyici şablonları (muhtemelen ayrı bir iş parçacığında) ve sonucunu almak için gelecek > Standart üstbilgiyi ekleyin. Sonuç, işlev tarafından döndürülen değer ya da işlev tarafından yayılan ancak işlevde yakalanmayan bir özel durumdur.

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

Şablon işlevi `async` ve şablon sınıfları `promise` ve `packaged_task` zaman uyumsuz sağlayıcılardır. Şablon sınıfları `future` ve `shared_future` zaman uyumsuz dönüş nesnelerini açıkla.

`promise`Şablon sınıflarının `future`her biri, ve `shared_future` **void** türü için bir özelleştirmeye sahiptir ve bir değeri başvuruya göre depolamaya ve almaya yönelik kısmi bir özelleşmeye sahiptir. Bu uzmanlıklar, birincil şablondan yalnızca, döndürülen değeri depolayan ve alan işlevlerin imzalarındaki ve semantiklerinden farklıdır.

Geriye dönük uyumluluk `future` için `shared_future` korunan bir durum dışında, şablon sınıfları ve yok edicilerin hiçbir şekilde engellenmez: İle `future` `shared_future` `.get()` başlatılan bir göreve eklenen diğer tüm vadeli sürelerden farklı olarak, yok edicinin, görev tamamlanmadıysa, yıkıcı engeller; diğer bir deyişle, bu iş parçacığının henüz çağırmadıysa veya `std::async` `.wait()`ve görev hala çalışıyor. Aşağıdaki kullanılabilirlik notunun açıklaması `std::async` taslak standardında eklenmiştir: "[Note: Std:: Async öğesinden daha sonra elde edilen bir işlem yerel kapsam dışına taşınırsa, geleceğin kullanıldığı diğer kod, gelecekteki yok edicinin, daha sonra tüm diğer durumlarda, `future` `shared_future` paylaşılan durumun başlamaya engel olabileceğini göz önünde bulundurulmalıdır. — unutmayın. yok ediciler gereklidir ve hiçbir şekilde engellenmeme garantisi vardır.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[future Sınıfı](../standard-library/future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar.|
|[future_error Sınıfı](../standard-library/future-error-class.md)|Nesneleri yöneten `future` türdeki yöntemlerle oluşturulabilecek bir özel durum nesnesi tanımlar.|
|[packaged_task Sınıfı](../standard-library/packaged-task-class.md)|Çağrı sarmalayıcısı olan ve çağrı imzası `Ty(ArgTypes...)`olan zaman uyumsuz sağlayıcıyı açıklar. İlişkili zaman uyumsuz durumu, olası sonucun yanı sıra çağrılabilir nesnesinin bir kopyasını tutar.|
|[promise Sınıfı](../standard-library/promise-class.md)|Zaman uyumsuz sağlayıcıyı açıklar.|
|[shared_future Sınıfı](../standard-library/shared-future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar. Bir `future` nesnenin aksine, zaman uyumsuz bir sağlayıcı herhangi bir `shared_future` sayıda nesneyle ilişkilendirilebilir.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[is_error_code_enum Yapısı](../standard-library/is-error-code-enum-structure.md)|`future_errc` Öğesinin`error_code`depolanması için uygun olduğunu gösteren özelleşme.|
|[uses_allocator Yapısı](../standard-library/uses-allocator-structure.md)|Her zaman true tutan özelleştirme.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[async](../standard-library/future-functions.md#async)|Zaman uyumsuz sağlayıcıyı temsil eder.|
|[future_category](../standard-library/future-functions.md#future_category)|Nesneler ile `error_category` `future` ilişkili hataları karakterlendirir nesnesine bir başvuru döndürür.|
|[make_error_code](../standard-library/future-functions.md#make_error_code)|Hataları karakterleştiren `error_category` `error_code` nesnesinesahipbiroluşturur`future` .|
|[make_error_condition](../standard-library/future-functions.md#make_error_condition)|Hataları karakterleştiren `error_category` `error_condition` nesnesinesahipbiroluşturur`future` .|
|[Kur](../standard-library/future-functions.md#swap)|Bir `promise` nesnenin ilişkili zaman uyumsuz durumunu başka bir nesneyle değiş tokuş eder.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[future_errc](../standard-library/future-enums.md#future_errc)|`future_error` Sınıfı tarafından bildirilen hatalar için simgesel adlar sağlar.|
|[future_status](../standard-library/future-enums.md#future_status)|, Zaman aşımına uğramayı bekleyen bir işlevin döndürebileceği nedenlerle sembolik adlar sağlar.|
|[Man](../standard-library/future-enums.md#launch)|Şablon işlevi `async`için olası modları açıklayan bir bit maskesi türünü temsil eder.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
