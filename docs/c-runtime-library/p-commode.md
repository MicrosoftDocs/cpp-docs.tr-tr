---
title: __p__commode
ms.date: 11/04/2016
api_name:
- __p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: e3121c127c3ebf0f5fccdeb7ae0f67d0164d0965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171482"
---
# <a name="__p__commode"></a>__p__commode

Dosya g/ç işlemleri için varsayılan *dosya kaydetme modunu* belirten `_commode` genel değişkenine işaret eder.

## <a name="syntax"></a>Sözdizimi

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_commode` genel değişkenine yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__commode` işlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya tamamlama modu, kritik verilerin diske ne zaman yazıldığını belirtir. Daha fazla bilgi için bkz. [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__commode|iç. h|
