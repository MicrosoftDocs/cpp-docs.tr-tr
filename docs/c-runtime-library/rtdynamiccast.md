---
title: __RTDynamicCast | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __RTDynamicCast
apilocation:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords: __RTDynamicCast
dev_langs: C++
helpviewer_keywords: __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b648d2f0f63a13451d5625c99e5bf614c8402017
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rtdynamiccast"></a>__RTDynamicCast
Çalışma zamanı uygulaması [dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `inptr`  
 Çok biçimli nesnesine işaretçi.  
  
 `VfDelta`  
 Nesnedeki sanal işlev işaretçisi uzaklığı.  
  
 `SrcType`  
 Tarafından için statik nesne türünü işaret `inptr` parametresi.  
  
 `TargetType`  
 Cast hedeflenen sonucu.  
  
 `isReference`  
 `true`Giriş başvuru ise; `false` giriş işaretçi ise.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi başarılı olursa uygun alt nesnesine; Aksi takdirde NULL.  
  
## <a name="exceptions"></a>Özel Durumlar  
 `bad_cast()`varsa girdisi `dynamic_cast<>` başvurudur ve dönüştürme başarısız.  
  
## <a name="remarks"></a>Açıklamalar  
 Dönüştürür `inptr` türünde bir nesneye `TargetType`. Türü `inptr` bir işaretçi olmalıdır `TargetType` bir işaretçi ya da bir l-değeri ise `TargetType` başvurudur. `TargetType`bir işaretçi veya önceden tanımlanmış sınıf türü için bir başvuru ya da bir işaretçi void olması gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__RTDynamicCast|rtti.h|