---
title: ___lc_locale_name_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 243fcd75c657125e001e4dc0544e9c315df1bd07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
İç CRT işlevi. Geçerli iş parçacığı yerel ayar adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli iş parçacığı yerel ayar adını içeren bir dize için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `___lc_locale_name_func`Geçerli yerel ayar adı iş parçacığı yerel depolama biriminden için CRT verileri almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi veya [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevleri.  
  
 İç CRT işlevleri uygulamaya özel ve her değiştirilebilir. Biz kodunuzda bunların kullanılması önerilmez.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)