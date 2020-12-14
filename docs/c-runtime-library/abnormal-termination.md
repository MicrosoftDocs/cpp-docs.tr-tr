---
description: 'Hakkında daha fazla bilgi edinin: _abnormal_termination'
title: _abnormal_termination
ms.date: 11/04/2016
api_name:
- _abnormal_termination
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: 2fa4b82deeebda7624d8ac96be675efc100ae926
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224289"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

**`__finally`** Sistem, sonlandırma işleyicileri iç listesini yürütürken [try-finally ifadesinin](../cpp/try-finally-statement.md) bloğunun girilip girilmediğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Dönüş Değeri

**`true`** Sistem yığının *geri sarılıyor* ; Aksi takdirde, **`false`** .

## <a name="remarks"></a>Açıklamalar

Bu, geriye doğru olmayan özel durumları yönetmek için kullanılan bir iç işlevdir ve kullanıcı kodundan çağrılması amaçlanmamıştır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_abnormal_termination|excpt. h|

## <a name="see-also"></a>Ayrıca bkz.

[try-finally ekstresi](../cpp/try-finally-statement.md)
