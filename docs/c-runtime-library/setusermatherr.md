---
title: __setusermatherr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __setusermatherr
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __setusermatherr
dev_langs:
- C++
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eefd80ae9eafd20615d90a259af247b4bcb7ce0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setusermatherr"></a>__setusermatherr
Yerine matematik hataları işlemek için bir kullanıcı tarafından sağlanan rountine belirtir [_matherr](../c-runtime-library/reference/matherr.md) yordamı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pf`  
 Uygulaması işaretçi `_matherr` kullanıcı tarafından sağlanan.  
  
 Türü `pf` parametre olarak bildirilen `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__setusermatherr|matherr.c|