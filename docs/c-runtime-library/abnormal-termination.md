---
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
ms.openlocfilehash: a963f1059eccaddce9ec01cd53a07df668ee46c6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213664"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

**`__finally`** Sistem, sonlandırma işleyicileri iç listesini yürütürken [try-finally ifadesinin](../cpp/try-finally-statement.md) bloğunun girilip girilmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

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
