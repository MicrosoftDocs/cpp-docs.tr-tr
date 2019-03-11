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
ms.openlocfilehash: 213938fa830f0a924fa954d4a36a39b544473dd4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741292"
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

## <a name="see-also"></a>Ayrıca bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)
