---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: 983fbc190fb83b81534e3888c748c0bf9c235638
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404942"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Dahil `iostreams` standart üstbilgi \<iomanip > her birkaç manipülatörleri tanımlamak için tek bir bağımsız değişken alın.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Açıklamalar

Her biri bu manipülatörleri adlı belirtilmeyen bir türün döndürür `T1` aracılığıyla `T10`, her ikisi de aşırı `basic_istream` \< **Elem**, **Tr** > `::` [işleci >>](../standard-library/istream-operators.md#op_gt_gt) ve `basic_ostream` \< **Elem**, **Tr** > `::` [işleci <<](../standard-library/ostream-operators.md#op_lt_lt).

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|İsteğe bağlı olarak uluslararası biçiminde bir parasal miktarını alır.|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Saati zaman yapısını, belirtilen biçimi kullanarak alır.|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|İsteğe bağlı olarak uluslararası biçiminde bir parasal miktarını sağlar.|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Zaman yapısı ve kullanmak için bir biçim dizesi bir sürede sağlar.|
|[Teklif](../standard-library/iomanip-functions.md#quoted)|Dizeler ekleme ve çıkarma işleçleri ile kullanışlı gidiş dönüşü sağlar.|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Belirtilen bayraklar temizler.|
|[setbase](../standard-library/iomanip-functions.md#setbase)|Tamsayılar için temel olarak ayarlayın.|
|[setfill](../standard-library/iomanip-functions.md#setfill)|Sağa yaslanmış görüntüsündeki alanları doldurmak için kullanılan karakter ayarlar.|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Belirtilen bayraklar ayarlar.|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Duyarlık kayan nokta değerleri için ayarlar.|
|[setw](../standard-library/iomanip-functions.md#setw)|Görüntüleme alanının genişliğini belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
