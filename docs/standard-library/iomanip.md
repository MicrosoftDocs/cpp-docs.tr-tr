---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: b9da0de64bbb0ef48a6a9741ff941e6abda0e705
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449203"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Her birinin tek bir \<bağımsız değişken aldığı birkaç işlem tanımlamak için iomanıp > Standartüstbilgisiniekleyin.`iostreams`

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Açıklamalar

`T1` Bu işleçlerden her biri, ile `T10`çağrılan belirtilmemiş bir tür döndürür ve hem **elee**, **tr**> `basic_istream``::`[işleci > >](../standard-library/istream-operators.md#op_gt_gt) hem de \< `basic_ostream` **Eled**, trişleci><[<](../standard-library/ostream-operators.md#op_lt_lt).`::` \<

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|İsteğe bağlı olarak uluslararası biçimde parasal bir miktar alır.|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Belirtilen biçimi kullanarak zaman yapısında bir zaman alır.|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|İsteğe bağlı olarak uluslararası biçimde parasal bir miktar sağlar.|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Bir zaman yapısında ve kullanılacak biçim dizesinde bir zaman sağlar.|
|[tırnak işaretli](../standard-library/iomanip-functions.md#quoted)|Ekleme ve ayıklama işleçleri ile dizelerin kolay gidiş dönüşü sunar.|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Belirtilen bayrakları temizler.|
|[setbase](../standard-library/iomanip-functions.md#setbase)|Tamsayılar için taban ayarla.|
|[setfill](../standard-library/iomanip-functions.md#setfill)|Sağa hizalanmış bir ekranda boşlukları doldur, kullanılacak karakteri ayarlar.|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Belirtilen bayrakları ayarlar.|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Kayan nokta değerleri için duyarlığı ayarlar.|
|[setw](../standard-library/iomanip-functions.md#setw)|Görüntüleme alanının genişliğini belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
