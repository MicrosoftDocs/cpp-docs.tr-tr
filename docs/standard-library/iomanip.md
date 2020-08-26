---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: f3f6c4886d22c7cd12b29950c114fbcde8905c28
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845750"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

`iostreams` \<iomanip> Her birinin tek bir bağımsız değişken aldığı birkaç işlem tanımlamak için standart üstbilgiyi ekleyin.

## <a name="syntax"></a>Syntax

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Açıklamalar

Bu işleçlerden her biri `T1` `T10` , hem `basic_istream` \<**Elem**, **Tr**> `::` [işleç>>](../standard-library/istream-operators.md#op_gt_gt) hem de `basic_ostream` \<**Elem**, **Tr**> `::` [işleç<<](../standard-library/ostream-operators.md#op_lt_lt)aşırı yükleyen, ile çağrılan belirtilmemiş bir tür döndürür.

### <a name="manipulators"></a>Manipülatörleri

|Ad|Açıklama|
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
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
