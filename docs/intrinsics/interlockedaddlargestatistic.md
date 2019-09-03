---
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: de8c5b7dfd2462dddcb98324ebacc44c8148d85e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222095"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft 'a özgü**

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

## <a name="return-value"></a>Dönüş değeri

İkinci işlenenin değeri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İki ayrı kilitli yönerge olarak uygulandığından, içatomikdeğildir.`_InterlockedAddLargeStatistic` İç işleminin yürütülmesi sırasında başka bir iş parçacığında gerçekleşen atomik 64 bit okuma tutarsız bir değer okumasına neden olabilir.

`_InterlockedAddLargeStatistic`okuma/yazma engeli olarak davranır. Daha fazla bilgi için bkz. [_Readwriteengeli](../intrinsics/readwritebarrier.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
