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
ms.openlocfilehash: b66cf0df998b4e33a9f3425fdf0f260d163f423b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944719"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

Sistem, sonlandırma `__finally` işleyicileri iç listesini yürütürken [try-finally ifadesinin](../cpp/try-finally-statement.md) bloğunun girilip girilmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Dönüş Değeri

Sistem yığını *geri* alıyorsa **doğru** ; Aksi takdirde, **false**.

## <a name="remarks"></a>Açıklamalar

Bu, geriye doğru olmayan özel durumları yönetmek için kullanılan bir iç işlevdir ve kullanıcı kodundan çağrılması amaçlanmamıştır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_abnormal_termination|excpt. h|

## <a name="see-also"></a>Ayrıca bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)
