---
description: 'Hakkında daha fazla bilgi edinin: __p__commode'
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
ms.openlocfilehash: f3f779196b650d05bb16c0da652d47946fc2a10d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213630"
---
# <a name="__p__commode"></a>__p__commode

`_commode`Dosya g/ç işlemleri için varsayılan *dosya kaydetme modunu* belirten genel değişkene işaret eder.

## <a name="syntax"></a>Syntax

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_commode`Genel değişkene yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__commode`İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya tamamlama modu, kritik verilerin diske ne zaman yazıldığını belirtir. Daha fazla bilgi için bkz. [fflush](../c-runtime-library/reference/fflush.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p \_ _commode|iç. h|
