---
title: Concurrency::graphics Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: ef61c93e062b375377a0afe62aa7f622f6c0d4ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375606"
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics Ad Alanı

Grafik ad alanı türleri ve grafik programlama için tasarlanmış işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
namespace graphics;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad Alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency::graphics::direct3d Ad Alanı](concurrency-graphics-direct3d-namespace.md)|Direct3D birlikte çalışabilirlik için işlevler sağlar.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`uint`|Öğe türü için [uint_2 sınıfı](uint-2-class.md), [uint_3 sınıfı](uint-3-class.md), ve [uint_4 sınıfı](uint-4-class.md). Olarak tanımlanan `typedef unsigned int uint;`.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[address_mode numaralandırması](concurrency-graphics-namespace-enums.md#address_mode).|Doku örnekleme için desteklenen adres modlarını belirtir.|
|[filter_mode numaralandırması](concurrency-graphics-namespace-enums.md#filter_mode)|Doku örnekleme için desteklenen filtre modlarını belirtir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[texture Sınıfı](texture-class.md)|Bir doku Hızlandırıcı uzantı etki alanında bulunan veri var. Bu uzantı etki alanındaki her öğe için değişkenlerden oluşan bir koleksiyondur. Her değişken (şeritsiz int, int, kayan, çift) C++ ilkel türüne karşılık gelen bir değer tutuyor veya skalar türü norma veya unorm (graphics'de tanımlanan) ya da uygun kısa vektör türlerine concurrency::graphics içinde tanımlanan.|
|[writeonly_texture_view Sınıfı](writeonly-texture-view-class.md)|Bir writeonly_texture_view bir dokuya salt yazılır erişim sağlar.|
|[double_2 Sınıfı](double-2-class.md)|2 oluşan bir kısa vektörü temsil eder `double` değerleri.|
|[double_3 Sınıfı](double-3-class.md)|3 oluşan bir kısa vektörü temsil eder `double` değerleri.|
|[double_4 Sınıfı](double-4-class.md)|4 oluşan bir kısa vektörü temsil eder `double` değerleri.|
|[float_2 Sınıfı](float-2-class.md)|2 oluşan bir kısa vektörü temsil eder `float` değerleri.|
|[float_3 Sınıfı](float-3-class.md)|3 oluşan bir kısa vektörü temsil eder `float` değerleri.|
|[float_4 Sınıfı](float-4-class.md)|4 oluşan bir kısa vektörü temsil eder `float` değerleri.|
|[int_2 Sınıfı](int-2-class.md)|2 oluşan bir kısa vektörü temsil eder `int` değerleri.|
|[int_3 Sınıfı](int-3-class.md)|3 oluşan bir kısa vektörü temsil eder `int` değerleri.|
|[int_4 Sınıfı](int-4-class.md)|4 oluşan bir kısa vektörü temsil eder `int` değerleri.|
|[norm_2 Sınıfı](norm-2-class.md)|2 oluşan bir kısa vektörü temsil eder `norm` değerleri.|
|[norm_3 Sınıfı](norm-3-class.md)|3 oluşan bir kısa vektörü temsil eder `norm` değerleri.|
|[norm_4 Sınıfı](norm-4-class.md)|4 oluşan bir kısa vektörü temsil eder `norm` değerleri.|
|[uint_2 Sınıfı](uint-2-class.md)|2 oluşan bir kısa vektörü temsil eder `uint` değerleri.|
|[uint_3 Sınıfı](uint-3-class.md)|3 oluşan bir kısa vektörü temsil eder `uint` değerleri.|
|[uint_4 Sınıfı](uint-4-class.md)|4 oluşan bir kısa vektörü temsil eder `uint` değerleri.|
|[unorm_2 Sınıfı](unorm-2-class.md)|2 oluşan bir kısa vektörü temsil eder `unorm` değerleri.|
|[unorm_3 Sınıfı](unorm-3-class.md)|3 oluşan bir kısa vektörü temsil eder `unorm` değerleri.|
|[unorm_4 Sınıfı](unorm-4-class.md)|4 oluşan bir kısa vektörü temsil eder `unorm` değerleri.|
|[sampler Sınıfı](sampler-class.md)|Doku örnekleme için kullanılan örnekleyici yapılandırmasını temsil eder.|
|[short_vector Yapısı](short-vector-structure.md)|Kısa bir vektör değerleri uygulaması sağlar.|
|[short_vector_traits Yapısı](short-vector-traits-structure.md)|İçin bir kısa vektör türü ve uzunluğunu alınmasını sağlar.|
|[texture_view Sınıfı](texture-view-class.md)|Okuma erişimi ve bir doku yazma erişimi sağlar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[kopyalama](concurrency-graphics-namespace-functions.md#copy)|Fazla Yüklendi. Kaynak doku içeriğini hedef ana bilgisayar arabelleğine kopyalar.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Fazla Yüklendi. Zaman uyumsuz olarak kaynak doku içeriğini hedef ana bilgisayar arabelleğine kopyalar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** Eşzamanlılık

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
