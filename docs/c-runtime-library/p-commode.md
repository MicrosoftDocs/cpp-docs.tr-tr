---
title: __p__commode
ms.date: 4/2/2020
api_name:
- __p__commode
- _o___p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: 057a0146aed87a50fc2e8c444b97a8b7b51eada1
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919497"
---
# <a name="__p__commode"></a>__p__commode

Dosya g/ `_commode` ç işlemleri için varsayılan *dosya kaydetme modunu* belirten genel değişkene işaret eder.

## <a name="syntax"></a>Sözdizimi

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_commode` Genel değişkene yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__commode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya tamamlama modu, kritik verilerin diske ne zaman yazıldığını belirtir. Daha fazla bilgi için bkz. [fflush](../c-runtime-library/reference/fflush.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__commode|iç. h|
