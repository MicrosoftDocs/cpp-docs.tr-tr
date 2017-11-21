---
title: _InterlockedAddLargeStatistic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs: C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7930f1411c419fbf5f47164029fe42dd82455ff8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft özel**  
  
 İlk işleneni bir 64-bit değeri olduğu ınterlocked ek gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out]`Addend`  
 İlk işlenen ekleme işlemi için bir işaretçi. İşaret değer eklenmesi sonucu değiştirilir.  
  
 [in]`Value`  
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
 [X86 çakışıyor derleyici](../build/conflicts-with-the-x86-compiler.md)