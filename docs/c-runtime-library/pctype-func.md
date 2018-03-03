---
title: __pctype_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __pctype_func
dev_langs:
- C++
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 239779bf4515615f25ff83be9221b1040d936a7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pctypefunc"></a>__pctype_func
Karakter sınıflandırması bilgileri dizisi için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Karakter sınıflandırması bilgileri dizisi için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Karakter sınıflandırması tabloda yer alan bilgiler yalnızca dahili kullanım içindir ve karakter türü sınıflandırmak çeşitli işlevleri tarafından kullanılan `char`. Daha fazla bilgi için bkz: `Remarks` bölümünü [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__pctype_func|CType.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)