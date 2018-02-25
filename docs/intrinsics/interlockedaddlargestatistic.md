---
title: _InterlockedAddLargeStatistic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa3a9a88520516051b067d45f4e18a92946c1346
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft Specific**  
  
 İlk işleneni bir 64-bit değeri olduğu ınterlocked ek gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out] `Addend`  
 İlk işlenen ekleme işlemi için bir işaretçi. İşaret değer eklenmesi sonucu değiştirilir.  
  
 [in] `Value`  
 İkinci işlenen; ilk işlenen eklenecek değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İkinci işlenen değeri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İki kilitli yönergeleri ayrı olarak uygulanan olduğundan bu iç atomik değil. Başka bir iş parçacığında bu yürütme sırasında iç oluşur atomik bir 64-bit okuma okunan tutarsız bir değerinde neden olabilir.  
  
 Bu işlev bir okuma-yazma engelle davranır. Daha fazla bilgi için bkz: [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)