---
title: '&lt;sınırları&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84437f53d8685c842e102fac3da7b062058bb20e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltlimitsgt"></a>&lt;Sınırları&gt;

Şablon sınıfı tanımlayan `numeric_limits` ve kayan nokta temsili ilgili ve yuvarlama iki numaralandırmalar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <limits>

```

## <a name="remarks"></a>Açıklamalar

Açık özelleştirmeleri `numeric_limits` sınıfı karakter, tamsayı ve kayan nokta türleri gibi temel türleri, birçok özelliklerini açıklar ve `bool` C++ kuralları tarafından sabit yerine tanımlanan uygulama olan dili. Özellikler bölümünde açıklanan \<sınırları > doğruluğu, minimum ve maksimum dahil yuvarlama ve türü hataları sinyal Beyanları boyuta sahip.

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Numaralandırma Normalleştirilmemiş kayan noktalı bir sayıyı temsil eden bir uygulama seçebileceğiniz çeşitli yöntemlerini açıklar — normalleştirilmiş değeri olarak göstermek için çok küçük bir:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Numaralandırma bir tamsayı değeri kayan noktalı bir sayıyı yuvarlama uygulaması seçebileceğiniz çeşitli yöntemleri açıklar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[numeric_limits Sınıfı](../standard-library/numeric-limits-class.md)|Şablon sınıfı yerleşik sayısal türler aritmetik özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
