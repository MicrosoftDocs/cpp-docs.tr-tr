---
title: Concurrency::graphics Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: 942b3bbace85fa297bba6cd4b509f67006a4aed3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226743"
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics Ad Alanı

Grafik ad alanı, grafik programlama için tasarlanmış türleri ve işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace graphics;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency:: Graphics::d irect3d ad alanı](concurrency-graphics-direct3d-namespace.md)|Direct3D birlikte çalışma için işlevler sağlar.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`uint`|[Uint_2 sınıfının](uint-2-class.md), [uint_3 sınıfının](uint-3-class.md)ve [uint_4 sınıfının](uint-4-class.md)öğe türü. Olarak tanımlanır `typedef unsigned int uint;` .|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[Address_mode numaralandırması](concurrency-graphics-namespace-enums.md#address_mode).|Doku örnekleme için desteklenen adres modlarını belirtir.|
|[filter_mode numaralandırması](concurrency-graphics-namespace-enums.md#filter_mode)|Doku örnekleme için desteklenen filtre modlarını belirtir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[doku sınıfı](texture-class.md)|Doku, kapsam etki alanındaki bir accelerator_view veri toplamasının toplamıdır. Bir uzantı etki alanındaki her öğe için bir değişken koleksiyonudur. Her değişken, C++ temel türü (işaretsiz int, int, float, Double) veya skaler tür norm veya unorm (concurrency:: Graphics içinde tanımlanan) veya concurrency:: Graphics içinde tanımlanan uygun kısa vektör türlerine karşılık gelen bir değeri barındırır.|
|[writeonly_texture_view sınıfı](writeonly-texture-view-class.md)|Writeonly_texture_view bir dokuya WriteOnly erişimi sağlar.|
|[double_2 Sınıfı](double-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder **`double`** .|
|[double_3 sınıfı](double-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder **`double`** .|
|[double_4 sınıfı](double-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder **`double`** .|
|[float_2 sınıfı](float-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder **`float`** .|
|[float_3 sınıfı](float-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder **`float`** .|
|[float_4 sınıfı](float-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder **`float`** .|
|[int_2 sınıfı](int-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder **`int`** .|
|[int_3 Sınıfı](int-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder **`int`** .|
|[int_4 sınıfı](int-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder **`int`** .|
|[norm_2 sınıfı](norm-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder `norm` .|
|[norm_3 sınıfı](norm-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder `norm` .|
|[norm_4 sınıfı](norm-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder `norm` .|
|[uint_2 sınıfı](uint-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder `uint` .|
|[uint_3 sınıfı](uint-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder `uint` .|
|[uint_4 sınıfı](uint-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder `uint` .|
|[unorm_2 sınıfı](unorm-2-class.md)|2 değerden oluşan bir kısa vektörü temsil eder `unorm` .|
|[unorm_3 sınıfı](unorm-3-class.md)|3 değerden oluşan kısa bir vektörü temsil eder `unorm` .|
|[unorm_4 Sınıfı](unorm-4-class.md)|4 değerden oluşan kısa bir vektörü temsil eder `unorm` .|
|[örnekleyici sınıfı](sampler-class.md)|Doku örnekleme için kullanılan örnekleyici yapılandırmasını temsil eder.|
|[short_vector Yapısı](short-vector-structure.md)|Kısa bir değer vektörünün temel bir uygulamasını sağlar.|
|[short_vector_traits Yapısı](short-vector-traits-structure.md)|Kısa bir vektörün uzunluğunu ve türünü almak için sağlar.|
|[texture_view sınıfı](texture-view-class.md)|Bir dokuya okuma erişimi ve yazma erişimi sağlar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[kopya](concurrency-graphics-namespace-functions.md#copy)|Fazla Yüklendi. Kaynak dokusunun içeriğini hedef ana bilgisayar arabelleğine kopyalar.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Fazla Yüklendi. Zaman uyumsuz olarak kaynak dokusunun içeriğini hedef ana bilgisayar arabelleğine kopyalar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Zamanlı

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
