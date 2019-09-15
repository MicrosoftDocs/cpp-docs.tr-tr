---
title: __pctype_func
ms.date: 11/04/2016
api_name:
- __pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: f5dae74dd601df1dc737293a181eca60f5cd23f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944037"
---
# <a name="__pctype_func"></a>__pctype_func

Bir karakter sınıflandırma bilgileri dizisine bir işaretçi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Dönüş Değeri

Karakter sınıflandırma bilgileri dizisine yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Karakter sınıflandırma tablosundaki bilgiler yalnızca dahili kullanım içindir ve türü `char`karakterleri sınıflandırmakta olan çeşitli işlevler tarafından kullanılır. Daha fazla bilgi için `Remarks` [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)öğesinin bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__pctype_func|CType. h|

## <a name="see-also"></a>Ayrıca bkz.

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
