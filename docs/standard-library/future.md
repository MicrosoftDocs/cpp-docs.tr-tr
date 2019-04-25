---
title: '&lt;Gelecekte&gt;'
ms.date: 11/04/2016
f1_keywords:
- <future>
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
ms.openlocfilehash: 189a9f16b65ae74fc2a86bee62bf8bd548c486aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159866"
---
# <a name="ltfuturegt"></a>&lt;Gelecekte&gt;

Standart üst bilgiyi dahil \<gelecekteki > şablon sınıfları ve çalışan bir işlev basitleştiren destek şablonları tanımlamak için — ayrı bir iş parçacığı, büyük olasılıkla — ve sonucu alınıyor. , İşlev tarafından döndürülen değer veya işlev tarafından yayınlanan ancak işlev yakalanmamış özel durum oluşur.

Diğer ConcRT mekanizmaları ile birlikte kullanabilirsiniz, böylece bu başlığı eşzamanlılık çalışma zamanı (ConcRT) kullanır. ConcRT hakkında daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
#include <future>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Derlenmiş kodda **/CLR**, bu başlığı engellenir.

Bir *zaman uyumsuz sağlayıcıyı* işlev çağrısının sonucunu depolar. Bir *zaman uyumsuz dönüş nesnesi* işlev çağrısının sonucunu almak için kullanılır. Bir *ilişkili zaman uyumsuz durumu* bir zaman uyumsuz sağlayıcıyı ve bir veya daha fazla zaman uyumsuz dönüş nesneleri arasındaki iletişimi sağlar.

Bir programı ilişkili zaman uyumsuz durum nesneleri doğrudan oluşturmaz. Program, sağlayıcı ile ilişkili zaman uyumsuz durumu paylaşan bir zaman uyumsuz dönüş nesnesi oluşturur ve ihtiyaç duyduğu her zaman uyumsuz bir sağlayıcı oluşturur. Zaman uyumsuz sağlayıcıları ve zaman uyumsuz dönüş nesneleri, paylaşılan ilişkili zaman uyumsuz durumu tutan nesneleri yönetin. İlişkili zaman uyumsuz duruma başvuran son nesnenin yayımlandığında, ilişkili zaman uyumsuz durumu tutan nesne yok edilir.

Zaman uyumsuz bir sağlayıcı ya hiçbir ilişkili zaman uyumsuz duruma sahip bir zaman uyumsuz dönüş nesne *boş*.

İlişkili bir zaman uyumsuz durumu *hazır* yalnızca zaman uyumsuz sağlayıcısını bir dönüş değeri depolanan veya bir özel durum depolanan varsa.

Şablon işlevi `async` ve şablon sınıfları `promise` ve `packaged_task` zaman uyumsuz sağlayıcılarıdır. Şablon sınıfları `future` ve `shared_future` zaman uyumsuz dönüş nesneleri tanımlar.

Her bir şablon sınıfı `promise`, `future`, ve `shared_future` türü için bir uzmanlığı olan **void** ve depolamak ve başvuruya göre bir değer almak için kısmi özelleştirme. Bu uzmanlıklar birincil şablonunda yalnızca imzalar ve döndürülen değer depolanıp işlevleri semantikleri farklıdır.

Şablon sınıfları `future` ve `shared_future` hiçbir zaman kendi yıkıcılarda dışında geriye dönük uyumluluk için korunur bir durumda engelle: Diğer tüm gelecek aksine için bir `future`— veya son `shared_future`— kullanmaya bir göreve ekli `std::async`, yok edici blokları görevi tamamlanmadıysa; bu iş parçacığı henüz arama diğer bir deyişle, bunu engeller `.get()` veya `.wait()`ve görev hala çalışıyor. Aşağıdaki kullanılabilirlik notun açıklaması için eklenmiş olan `std::async` taslak standart: "[Not: Yerel kapsamı dışında Std::Async ' elde edilen gelecek taşınırsa, gelecek kullanan diğer kod geleceğe ait yok Edicisi paylaşılan durum hazır olmasını engelleyebilir bilmeniz gerekir; son Not] "diğer tüm durumlarda `future` ve `shared_future` yok ediciler gerekmez ve hiçbir zaman engellememe garanti edilir.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[future Sınıfı](../standard-library/future-class.md)|Bir zaman uyumsuz dönüş nesnesi tanımlar.|
|[future_error Sınıfı](../standard-library/future-error-class.md)|Türlerinin yönetme yöntemleri tarafından oluşturulan bir özel durum nesnesi açıklar `future` nesneleri.|
|[packaged_task Sınıfı](../standard-library/packaged-task-class.md)|Bir zaman uyumsuz bir çağrı sarmalayıcı sağlayıcısını açıklar ve çağrı imzası `Ty(ArgTypes...)`. İlişkili zaman uyumsuz durumuna olası sonucu yanı sıra kendi çağrılabilir nesnesinin bir kopyasını tutar.|
|[promise Sınıfı](../standard-library/promise-class.md)|Zaman uyumsuz bir sağlayıcısını açıklar.|
|[shared_future Sınıfı](../standard-library/shared-future-class.md)|Bir zaman uyumsuz dönüş nesnesi tanımlar. Tersine ile bir `future` nesnesi, zaman uyumsuz bir sağlayıcı herhangi bir sayı ile ilişkilendirilebilir `shared_future` nesneleri.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[is_error_code_enum Yapısı](../standard-library/is-error-code-enum-structure.md)|Bildiren bir uzmanlık `future_errc` depolamak için uygun bir `error_code`.|
|[uses_allocator Yapısı](../standard-library/uses-allocator-structure.md)|Her zaman korumadıkça özelleştirmesi.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[async](../standard-library/future-functions.md#async)|Zaman uyumsuz bir sağlayıcısını temsil eder.|
|[future_category](../standard-library/future-functions.md#future_category)|Bir başvuru döndürür `error_category` ilişkili hataları nesnesi `future` nesneleri.|
|[make_error_code](../standard-library/future-functions.md#make_error_code)|Oluşturur bir `error_code` olan `error_category` nesnesi `future` hataları.|
|[make_error_condition](../standard-library/future-functions.md#make_error_condition)|Oluşturur bir `error_condition` olan `error_category` nesnesi `future` hataları.|
|[değiştirme](../standard-library/future-functions.md#swap)|Bir ilişkili zaman uyumsuz durumu değiştirir `promise` , başka bir nesne.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[future_errc](../standard-library/future-enums.md#future_errc)|Tarafından bildirilen hataları için simgesel adlar sağlar `future_error` sınıfı.|
|[future_status](../standard-library/future-enums.md#future_status)|Zamanlanmış bekleme işlevi döndürebilir nedenleri için simgesel adlar sağlar.|
|[başlatma](../standard-library/future-enums.md#launch)|Şablon işlevi için olası modları açıklar bir bit maskesi türünü temsil eden `async`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
