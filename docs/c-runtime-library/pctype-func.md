---
title: __pctype_func
ms.date: 4/2/2020
api_name:
- __pctype_func
- _o___pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 67447823b0322e647784cdbe0f3f7228e1c5fb34
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919239"
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

Karakter sınıflandırma tablosundaki bilgiler yalnızca dahili kullanım içindir ve türü `char`karakterleri sınıflandırmakta olan çeşitli işlevler tarafından kullanılır. Daha fazla bilgi için `Remarks` [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)bölümüne bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__pctype_func|CType. h|

## <a name="see-also"></a>Ayrıca bkz.

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
