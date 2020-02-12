---
title: Concurrency::graphics Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: c7e3b245c8d9e6ba0c563a63910fadd678523087
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139445"
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics Ad Alanı

Grafik ad alanı, grafik programlama için tasarlanmış türleri ve işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace graphics;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad Alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency::graphics::direct3d Ad Alanı](concurrency-graphics-direct3d-namespace.md)|Direct3D birlikte çalışma için işlevler sağlar.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`uint`|[Uint_2 sınıfının](uint-2-class.md), [uint_3 sınıfının](uint-3-class.md)ve [uint_4 sınıfının](uint-4-class.md)öğe türü. `typedef unsigned int uint;`olarak tanımlanır.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[Address_mode numaralandırması](concurrency-graphics-namespace-enums.md#address_mode).|Doku örnekleme için desteklenen adres modlarını belirtir.|
|[filter_mode numaralandırması](concurrency-graphics-namespace-enums.md#filter_mode)|Doku örnekleme için desteklenen filtre modlarını belirtir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[texture Sınıfı](texture-class.md)|Doku, kapsam etki alanındaki bir accelerator_view veri toplamasının toplamıdır. Bir uzantı etki alanındaki her öğe için bir değişken koleksiyonudur. Her değişken, ilkel tür (işaretsiz C++ int, int, float, Double) veya skaler tür norm veya unorm (concurrency:: Graphics içinde tanımlanan) veya concurrency:: Graphics içinde tanımlanan uygun kısa vektör türleri için karşılık gelen bir değer barındırır.|
|[writeonly_texture_view Sınıfı](writeonly-texture-view-class.md)|Writeonly_texture_view bir dokuya WriteOnly erişimi sağlar.|
|[double_2 Sınıfı](double-2-class.md)|2 `double` değerlerinin kısa vektörünü temsil eder.|
|[double_3 Sınıfı](double-3-class.md)|3 `double` değerden oluşan kısa bir vektörü temsil eder.|
|[double_4 Sınıfı](double-4-class.md)|4 `double` değerinin kısa bir vektörünü temsil eder.|
|[float_2 Sınıfı](float-2-class.md)|2 `float` değerlerinin kısa vektörünü temsil eder.|
|[float_3 Sınıfı](float-3-class.md)|3 `float` değerden oluşan kısa bir vektörü temsil eder.|
|[float_4 Sınıfı](float-4-class.md)|4 `float` değerinin kısa bir vektörünü temsil eder.|
|[int_2 Sınıfı](int-2-class.md)|2 `int` değerlerinin kısa vektörünü temsil eder.|
|[int_3 Sınıfı](int-3-class.md)|3 `int` değerden oluşan kısa bir vektörü temsil eder.|
|[int_4 Sınıfı](int-4-class.md)|4 `int` değerinin kısa bir vektörünü temsil eder.|
|[norm_2 Sınıfı](norm-2-class.md)|2 `norm` değerlerinin kısa vektörünü temsil eder.|
|[norm_3 Sınıfı](norm-3-class.md)|3 `norm` değerden oluşan kısa bir vektörü temsil eder.|
|[norm_4 Sınıfı](norm-4-class.md)|4 `norm` değerinin kısa bir vektörünü temsil eder.|
|[uint_2 Sınıfı](uint-2-class.md)|2 `uint` değerlerinin kısa vektörünü temsil eder.|
|[uint_3 Sınıfı](uint-3-class.md)|3 `uint` değerden oluşan kısa bir vektörü temsil eder.|
|[uint_4 Sınıfı](uint-4-class.md)|4 `uint` değerinin kısa bir vektörünü temsil eder.|
|[unorm_2 Sınıfı](unorm-2-class.md)|2 `unorm` değerlerinin kısa vektörünü temsil eder.|
|[unorm_3 Sınıfı](unorm-3-class.md)|3 `unorm` değerden oluşan kısa bir vektörü temsil eder.|
|[unorm_4 Sınıfı](unorm-4-class.md)|4 `unorm` değerinin kısa bir vektörünü temsil eder.|
|[sampler Sınıfı](sampler-class.md)|Doku örnekleme için kullanılan örnekleyici yapılandırmasını temsil eder.|
|[short_vector Yapısı](short-vector-structure.md)|Kısa bir değer vektörünün temel bir uygulamasını sağlar.|
|[short_vector_traits Yapısı](short-vector-traits-structure.md)|Kısa bir vektörün uzunluğunu ve türünü almak için sağlar.|
|[texture_view Sınıfı](texture-view-class.md)|Bir dokuya okuma erişimi ve yazma erişimi sağlar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[kopya](concurrency-graphics-namespace-functions.md#copy)|Fazla Yüklendi. Kaynak dokusunun içeriğini hedef ana bilgisayar arabelleğine kopyalar.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Fazla Yüklendi. Zaman uyumsuz olarak kaynak dokusunun içeriğini hedef ana bilgisayar arabelleğine kopyalar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Zamanlı

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
