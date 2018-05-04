---
title: __p__commode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e91c03f619be1d0f1d8ad23f3b8d60e1be30cfb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="pcommode"></a>__p__commode
İşaret `_commode` varsayılan belirtir genel değişkeni *dosya yürütme modu* dosya g/ç işlemleri için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi `_commode` genel değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 `__p__commode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.  
  
 Dosya Yürütme modunu belirtir zaman kritik veriler yazılır diske. Daha fazla bilgi için bkz: [fflush](../c-runtime-library/reference/fflush.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__p\__commode|internal.h|