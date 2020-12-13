---
description: 'Hakkında daha fazla bilgi edinin: _InterlockedAddLargeStatistic'
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 52ca32d0f9b08d638a66923f8f0204eb515b447e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336881"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft'a Özgü**

İlk işlenenin 64 bitlik bir değer olduğu bir kenetlenmiş ekleme işlemi gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```C
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

### <a name="parameters"></a>Parametreler

*Doğrusal formülündeki toplanan*\
[in, out] Ekleme işlemine ilk işlenenin işaretçisi. İşaret edilen değer, ekleme sonucuyla değiştirilmiştir.

*Deeri*\
'ndaki İkinci işlenen; ilk işlenene eklenecek değer.

## <a name="return-value"></a>Döndürülen değer

İkinci işlenenin değeri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_InterlockedAddLargeStatistic`İki ayrı kilitli yönerge olarak uygulandığından, iç atomik değildir. İç işleminin yürütülmesi sırasında başka bir iş parçacığında gerçekleşen atomik 64 bit okuma tutarsız bir değer okumasına neden olabilir.

`_InterlockedAddLargeStatistic` okuma/yazma engeli olarak davranır. Daha fazla bilgi için bkz. [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
