---
title: '&lt;Gelecekteki&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <future>
dev_langs:
- C++
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37e5e2ceff83704632a77ef0fb1eedecaa9e678b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847201"
---
# <a name="ltfuturegt"></a>&lt;Gelecek&gt;

Standart üstbilgisini \<gelecekteki > şablon sınıfları ve bir işlev çalıştıran basitleştirmek destekleyen şablonları tanımlamak için — büyük olasılıkla ayrı bir iş parçacığı içinde — ve sonucu alınıyor. , İşlev tarafından döndürülen değer veya işlev tarafından gösterilen ancak işlevinde yakalandı bir özel durum oluşur.

Bu üst eşzamanlılık çalışma zamanı (ConcRT) kullanır, böylece diğer ConcRT mekanizmaları ile birlikte kullanabilirsiniz. ConcRT hakkında daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Sözdizimi

```cpp
#include <future>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.

Bir *zaman uyumsuz sağlayıcısı* işlev çağrısının sonucunu depolar. Bir *zaman uyumsuz dönüş nesnesi* işlev çağrısının sonucunu almak için kullanılır. Bir *zaman uyumsuz durum ilişkili* zaman uyumsuz bir sağlayıcı ve bir veya daha fazla zaman uyumsuz dönüş nesneler arasında iletişimi sağlar.

Bir program herhangi bir ilişkili zaman uyumsuz durum nesne doğrudan oluşturmaz. Program bir gerekir ve değerinden sağlayıcı ile ilişkili zaman uyumsuz durumuna paylaşan bir zaman uyumsuz dönüş nesnesi oluşturur her zaman uyumsuz bir sağlayıcı oluşturur. Zaman uyumsuz sağlayıcıları ve zaman uyumsuz dönüş nesneleri kendi paylaşılan zaman uyumsuz durum ilişkili tutun nesneleri yönetin. İlişkili zaman uyumsuz durum başvuran son nesne yayımlandığında, ilişkili zaman uyumsuz durumu tutan nesnesi yok.

Zaman uyumsuz bir sağlayıcı veya ilişkili hiçbir zaman uyumsuz durumuna sahip bir zaman uyumsuz dönüş nesne *boş*.

İlişkili bir zaman uyumsuz durum *hazır* zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanır.

Şablon işlevi `async` ve şablon sınıfları `promise` ve `packaged_task` zaman uyumsuz sağlayıcılarıdır. Şablon sınıfları `future` ve `shared_future` zaman uyumsuz dönüş nesneleri tanımlar.

Her şablon sınıfları `promise`, `future`, ve `shared_future` türü için bir uzmanlık sahip `void` ve depolamak ve almak için kullanılan bir değer başvuruya göre bir kısmi uzmanlığı. Bu özelleştirmeleri birincil şablonda yalnızca imzalar ve döndürülen değer depolanıp işlevleri semantiği farklıdır.

Şablon sınıfları `future` ve `shared_future` hiçbir zaman kendi yıkıcılarda dışında geriye dönük uyumluluk için korunan bir durumda engelle: diğer vadeli aksine için bir `future`— ya da son `shared_future`— bir göreve bağlı kullanmaya `std::async`, yıkıcı blokları görevi tamamlanmadıysa; bu iş parçacığı henüz arama diğer bir deyişle, onu engeller `.get()` veya `.wait()` ve görev hala çalışıyor. Aşağıdaki kullanılabilirlik Not açıklaması için eklenen `std::async` taslak standart: "[Not: std::async alınan gelecek yerel kapsamı dışında taşınırsa, gelecek kullanan başka bir kod gelecek 's yıkıcı engelleyebilir bilmeniz gerekir Paylaşılan durum hazır hale — son Not] "diğer durumlarda `future` ve `shared_future` Yıkıcılar gereklidir ve hiçbir zaman engellemek için garanti.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[future Sınıfı](../standard-library/future-class.md)|Zaman uyumsuz dönüş nesneyi açıklar.|
|[future_error Sınıfı](../standard-library/future-error-class.md)|Yönetme türleri yöntemleri ile oluşturulan bir özel durum nesnesi tanımlar `future` nesneleri.|
|[packaged_task Sınıfı](../standard-library/packaged-task-class.md)|Çağrı sarmalayıcı olan bir zaman uyumsuz sağlayıcısını açıklar ve, çağrı imzası `Ty(ArgTypes...)`. İlişkili zaman uyumsuz durumuna olası sonuç yanı sıra kendi aranabilir nesnesinin bir kopyasını tutar.|
|[promise Sınıfı](../standard-library/promise-class.md)|Zaman uyumsuz bir sağlayıcısını açıklar.|
|[shared_future Sınıfı](../standard-library/shared-future-class.md)|Zaman uyumsuz dönüş nesneyi açıklar. Tersine ile bir `future` nesne, zaman uyumsuz bir sağlayıcı herhangi bir sayı ile ilişkilendirilebilir `shared_future` nesneleri.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[is_error_code_enum Yapısı](../standard-library/is-error-code-enum-structure.md)|Belirten uzmanlık `future_errc` depolamak için uygun bir `error_code`.|
|[uses_allocator Yapısı](../standard-library/uses-allocator-structure.md)|Uzmanlık her zaman geçerlidir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[async](../standard-library/future-functions.md#async)|Zaman uyumsuz bir sağlayıcısını temsil eder.|
|[future_category](../standard-library/future-functions.md#future_category)|Bir başvuru döndürür `error_category` ilişkili hataları belirtir nesne `future` nesneleri.|
|[make_error_code](../standard-library/future-functions.md#make_error_code)|Oluşturur bir `error_code` olan `error_category` belirtir nesne `future` hataları.|
|[make_error_condition](../standard-library/future-functions.md#make_error_condition)|Oluşturur bir `error_condition` olan `error_category` belirtir nesne `future` hataları.|
|[Değiştirme](../standard-library/future-functions.md#swap)|Bir ilişkili zaman uyumsuz durumu alış verişleri `promise` , başka bir nesne.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[future_errc](../standard-library/future-enums.md#future_errc)|Kaynakları tarafından bildirilen hataları için simgesel adları `future_error` sınıfı.|
|[future_status](../standard-library/future-enums.md#future_status)|Zamanlanmış bekleme işlevi döndürebilir nedeniyle simgesel adları sağlar.|
|[başlatma](../standard-library/future-enums.md#launch)|Şablon işlevi için olası modları tanımlayan bir bit maskesi türünü temsil eden `async`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
