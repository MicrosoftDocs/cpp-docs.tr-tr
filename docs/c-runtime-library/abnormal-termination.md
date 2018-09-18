---
title: _abnormal_termination | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e311c27d61eca82019f8069b0984557af02c74a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028213"
---
# <a name="abnormaltermination"></a>_abnormal_termination

Belirtir olup olmadığını `__finally` bloğu bir [try-finally deyimi](../cpp/try-finally-statement.md) sistem iç listesine sonlandırma işleyicileri yürütülürken girilir.

## <a name="syntax"></a>Sözdizimi

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`true` Sistem *geriye doğru izleme* yığını; Aksi takdirde `false`.

## <a name="remarks"></a>Açıklamalar

Bu durum, geriye doğru izleme özel durumlarını yönetmek için kullanılan bir iç işlevi ve kullanıcı kodundan çağrılmak üzere tasarlanmamıştır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>Ayrıca Bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)