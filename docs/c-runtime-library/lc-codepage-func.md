---
title: ___lc_codepage_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs: C++
helpviewer_keywords: ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d73f285647d3ef4947454fd4bc831b746ef754c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lccodepagefunc"></a>___lc_codepage_func
İç CRT işlevi. İş parçacığının geçerli kod sayfası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı geçerli kod sayfası.  
  
## <a name="remarks"></a>Açıklamalar  
 `___lc_codepage_func`Geçerli kod sayfası iş parçacığı yerel depolama biriminden için CRT verileri almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi.  
  
 A *kod sayfası* karakterleri tek tek tek baytlı veya çift baytlı kod eşlemedir. Farklı kod sayfaları genellikle bir dil veya bir grup diller için özelleştirilmiş farklı özel karakterler içerir. Kod sayfaları hakkında daha fazla bilgi için bkz: [kod sayfaları](../c-runtime-library/code-pages.md).  
  
 İç CRT işlevleri uygulamaya özel ve her değiştirilebilir. Biz kodunuzda bunların kullanılması önerilmez.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`___lc_codepage_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)