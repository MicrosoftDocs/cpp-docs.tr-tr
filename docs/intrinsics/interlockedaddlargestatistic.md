---
title: _InterlockedAddLargeStatistic
ms.date: 11/04/2016
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 6f9d599a8d7668c6c8a37846275e8338002589d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349494"
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft'a özgü**

İlk işleneni bir 64-bit değeri olduğu bir birbirine kenetlenmiş ek gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

#### <a name="parameters"></a>Parametreler

*Formülündeki toplanan*<br/>
[out içinde] Ekleme işlemi için ilk işlenen bir işaretçi. İşaret ettiği değer toplamın sonucunu tarafından değiştirilir.

*Değer*<br/>
[in] İkinci işlenenin; ilk işleneni eklenecek değer.

## <a name="return-value"></a>Dönüş Değeri

İkinci işlenenin değeri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Kilitli yönergeleri iki ayrı olarak uygulanan çünkü bu iç atomik değildir. Bu yürütme sırasında başka bir iş parçacığında içsel oluşan atomik bir 64-bit okuma okunan tutarsız bir değeri neden olabilir.

Bu işlev, bir okuma-yazma engel davranır. Daha fazla bilgi için [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)