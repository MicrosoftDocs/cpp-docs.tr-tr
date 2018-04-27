---
title: '&lt;rastgele&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: e3c5dba462b45589005a996e6226330882b29b15
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltrandomgt-functions"></a>&lt;rastgele&gt; işlevleri

## <a name="generate_canonical"></a>  generate_canonical

Kayan nokta değeri rastgele bir dizisini döndürür.

> [!NOTE]
> Bu işlev aralığındaki değerler döndürmesi gerektiğini ISO C++ Standart durumları [ `0`, `1`). Visual Studio henüz bu kısıtlaması ile uyumlu değil. Bu aralıkta değerlerini oluşturmak için geçici bir çözüm olarak kullanmak [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametreler

`RealType` Kayan nokta tamsayı türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

`Bits` Rastgele sayı üreticisinin.

`Gen` Rastgele sayı üreticisinin.

### <a name="remarks"></a>Açıklamalar

Şablon işlev çağrılarını `operator()` , `Gen` art arda ve kayan noktalı bir sayıyı döndürülen değerlerin paketleri `x` türü `RealType` Mantis bit cinsinden belirtilen sayıda topladı kadar `x`. Belirtilen sayı olan küçük `Bits` (hangi olmalıdır sıfır olmayan) ve Mantis bit tam sayı `RealType`. İlk çağrıda en düşük sıra bitleri sağlar. İşlevi döndürür `x`.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
