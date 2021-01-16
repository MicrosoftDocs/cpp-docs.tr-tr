---
description: 'Hakkında daha fazla bilgi edinin: __pctype_func'
title: __pctype_func
ms.date: 1/14/2021
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 492f4a4c6ff5a23c05c15267d7ac00f72bc6eb94
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242962"
---
# <a name="__pctype_func"></a>__pctype_func

Bir karakter sınıflandırma bilgileri dizisine bir işaretçi alır.

## <a name="syntax"></a>Syntax

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Dönüş Değeri

Karakter sınıflandırma bilgileri dizisine yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Karakter sınıflandırma tablosundaki bilgiler yalnızca dahili kullanım içindir ve türü karakterleri sınıflandırmakta olan çeşitli işlevler tarafından kullanılır **`char`** . Daha fazla bilgi için `Remarks` [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)bölümüne bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__pctype_func|CType. h|

## <a name="see-also"></a>Ayrıca bkz.

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
