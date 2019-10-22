---
title: '&lt;future &gt;'
ms.date: 11/04/2016
f1_keywords:
- <future>
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
ms.openlocfilehash: c852b3040a94035f6a84b1f717c3583fababbb2c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688029"
---
# <a name="ltfuturegt"></a>&lt;future &gt;

Sınıf şablonları tanımlamak için standart üst bilgi \<future > ekleyin (muhtemelen ayrı bir iş parçacığında) ve sonucunu almak için bir işlevi çalıştırmayı basitleştiren şablonları destekler. Sonuç, işlev tarafından döndürülen değer ya da işlev tarafından yayılan ancak işlevde yakalanmayan bir özel durumdur.

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

Şablon işlevi `async` ve sınıf şablonları `promise` ve `packaged_task` zaman uyumsuz sağlayıcılardır. Sınıf şablonları `future` ve `shared_future` zaman uyumsuz dönüş nesnelerini tanımlıyor.

@No__t_0, `future` ve `shared_future` sınıf şablonlarının her biri, **void** türü için bir özelleştirmeye ve bir değeri başvuruya göre depolamaya ve almaya yönelik kısmi bir özelleştirmeye sahiptir. Bu uzmanlıklar, birincil şablondan yalnızca, döndürülen değeri depolayan ve alan işlevlerin imzalarındaki ve semantiklerinden farklıdır.

Sınıf şablonları `future` ve `shared_future`, geri uyumluluk için korunmasının dışında, yok edicilerde hiçbir şekilde engellenmez: diğer tüm vadeli sürelerden farklı olarak, bir `future` veya en son `shared_future`, `std::async` ile başlatılan bir göreve eklenmiş , görev tamamlanmazsa yıkıcı engeller; diğer bir deyişle, bu iş parçacığı henüz `.get()` veya `.wait()` çağırmadıysa ve görev hala çalışıyorsa engeller. Aşağıdaki kullanılabilirlik notunun taslak standardında `std::async` açıklamasına eklenmiştir: "[Note: daha sonra std:: Async öğesinden elde edilen bir işlem yerel kapsam dışına taşınırsa, ileride bunu kullanan diğer kod, gelecekteki yıkıcının paylaşılan durum hazırlanıyor. — tüm diğer durumlarda, `future` ve `shared_future` yok ediciler gereklidir ve hiçbir zaman engellenmemelidir.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Name|Açıklama|
|----------|-----------------|
|[future Sınıfı](../standard-library/future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar.|
|[future_error Sınıfı](../standard-library/future-error-class.md)|@No__t_0 nesnelerini yöneten türlerin yöntemleriyle oluşturulabilecek bir özel durum nesnesi tanımlar.|
|[packaged_task Sınıfı](../standard-library/packaged-task-class.md)|Çağrı sarmalayıcısı olan ve çağrı imzası `Ty(ArgTypes...)` zaman uyumsuz bir sağlayıcıyı açıklar. İlişkili zaman uyumsuz durumu, olası sonucun yanı sıra çağrılabilir nesnesinin bir kopyasını tutar.|
|[promise Sınıfı](../standard-library/promise-class.md)|Zaman uyumsuz sağlayıcıyı açıklar.|
|[shared_future Sınıfı](../standard-library/shared-future-class.md)|Zaman uyumsuz bir dönüş nesnesi tanımlar. Bir `future` nesnesinin aksine, zaman uyumsuz bir sağlayıcı herhangi bir sayıda `shared_future` nesneyle ilişkilendirilebilir.|

### <a name="structures"></a>Yapılar

|Name|Açıklama|
|----------|-----------------|
|[is_error_code_enum Yapısı](../standard-library/is-error-code-enum-structure.md)|@No__t_0 bir `error_code` depolamak için uygun olduğunu belirten özelleşme.|
|[uses_allocator Yapısı](../standard-library/uses-allocator-structure.md)|Her zaman true tutan özelleştirme.|

### <a name="functions"></a>İşlevler

|Name|Açıklama|
|----------|-----------------|
|[async](../standard-library/future-functions.md#async)|Zaman uyumsuz sağlayıcıyı temsil eder.|
|[future_category](../standard-library/future-functions.md#future_category)|@No__t_1 nesneleriyle ilişkili hataları karakterlendirir `error_category` nesnesine bir başvuru döndürür.|
|[make_error_code](../standard-library/future-functions.md#make_error_code)|@No__t_2 hataları karakterlendirir `error_category` nesnesine sahip bir `error_code` oluşturur.|
|[make_error_condition](../standard-library/future-functions.md#make_error_condition)|@No__t_2 hataları karakterlendirir `error_category` nesnesine sahip bir `error_condition` oluşturur.|
|[Kur](../standard-library/future-functions.md#swap)|Bir `promise` nesnesinin ilişkili zaman uyumsuz durumunu başka bir nesneyle değiştirir.|

### <a name="enumerations"></a>Numaralandırmalar

|Name|Açıklama|
|----------|-----------------|
|[future_errc](../standard-library/future-enums.md#future_errc)|@No__t_0 sınıfı tarafından bildirilen hatalar için simgesel adlar sağlar.|
|[future_status](../standard-library/future-enums.md#future_status)|, Zaman aşımına uğramayı bekleyen bir işlevin döndürebileceği nedenlerle sembolik adlar sağlar.|
|[Man](../standard-library/future-enums.md#launch)|@No__t_0 şablon işlevi için olası modları açıklayan bir bit maskesi türünü temsil eder.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
