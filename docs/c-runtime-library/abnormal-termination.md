---
title: _abnormal_termination
ms.date: 11/04/2016
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
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: 231a5a521d9e234d3e31e6ccdbe98b207a89b3eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433549"
---
# <a name="abnormaltermination"></a>_abnormal_termination

Belirtir olup olmadığını `__finally` bloğu bir [try-finally deyimi](../cpp/try-finally-statement.md) sistem iç listesine sonlandırma işleyicileri yürütülürken girilir.

## <a name="syntax"></a>Sözdizimi

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Dönüş Değeri

**doğru** sistem *geriye doğru izleme* yığını; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Bu durum, geriye doğru izleme özel durumlarını yönetmek için kullanılan bir iç işlevi ve kullanıcı kodundan çağrılmak üzere tasarlanmamıştır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>Ayrıca Bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)