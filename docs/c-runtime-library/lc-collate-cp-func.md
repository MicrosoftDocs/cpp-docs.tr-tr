---
title: ___lc_collate_cp_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords: ___lc_collate_cp_func
dev_langs: C++
helpviewer_keywords: ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe7ff6ce073f84a87e2243ab98d3b99af0dfd22c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func
İç CRT işlevi. İş parçacığının geçerli harmanlama kod sayfası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İş parçacığının geçerli harmanlama kod sayfası.  
  
## <a name="remarks"></a>Açıklamalar  
 `___lc_collate_cp_func`Geçerli harmanlama kod sayfası iş parçacığı yerel depolama biriminden için CRT verileri almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi.  
  
 İç CRT işlevleri uygulamaya özel ve her değiştirilebilir. Biz kodunuzda bunların kullanılması önerilmez.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`___lc_collate_cp_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)