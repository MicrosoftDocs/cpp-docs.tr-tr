---
title: __p__fmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c520f81062f1bbbb295f17c6bc041afb8b5f2877
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389842"
---
# <a name="pfmode"></a>__p__fmode
İşaret `_fmode` varsayılan belirtir genel değişkeni *dosya çevirisi modu* dosya g/ç işlemleri için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi `_fmode` genel değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 `__p__fmode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.  
  
 Dosya çevirisi modu belirtir ya da `binary` veya `text` çeviri [_kurulum Aç](../c-runtime-library/reference/open-wopen.md) ve [_pipe](../c-runtime-library/reference/pipe.md) g/ç işlemleri. Daha fazla bilgi için bkz: [_fmode](../c-runtime-library/fmode.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__p\__fmode|stdlib.h|