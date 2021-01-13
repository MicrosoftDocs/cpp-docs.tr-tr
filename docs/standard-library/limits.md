---
description: 'Daha fazla bilgi edinin: &lt; sınırlar&gt;'
title: '&lt;değerleri&gt;'
ms.date: 11/04/2016
f1_keywords:
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: 23601b4b7f7ea06071a6b1f5fbd87ce0a0babce3
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126396"
---
# <a name="ltlimitsgt"></a>&lt;değerleri&gt;

Sınıf şablonunu `numeric_limits` ve kayan nokta temsilleri ve yuvarlama ile ilgili iki numaralandırma tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<limits>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Sınıfın açık Uzmanlıkları, `numeric_limits` karakter, tamsayı ve kayan nokta türleri de dahil olmak üzere temel türlerin birçok özelliğini ve **`bool`** C++ dilinin kuralları tarafından sabitlenemez. \<limits>Doğruluk, en düşük ve en büyük ölçekli temsiller, yuvarlama ve sinyal türü hatalarını içerir bölümünde açıklanan özellikler.

## <a name="members"></a>Üyeler

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Sabit listesi, bir uygulamanın, Normalleştirilmemiş bir kayan nokta değerini temsil etmek için seçebileceğiniz çeşitli yöntemleri açıklar; normalleştirilmiş bir değer olarak temsil etmek için çok küçük:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Sabit listesi, bir uygulamanın kayan nokta değerini bir tamsayı değerine yuvarlarken seçebileceği çeşitli yöntemleri açıklar.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[numeric_limits sınıfı](../standard-library/numeric-limits-class.md)|Sınıf şablonu, yerleşik sayısal türlerin aritmetik özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
