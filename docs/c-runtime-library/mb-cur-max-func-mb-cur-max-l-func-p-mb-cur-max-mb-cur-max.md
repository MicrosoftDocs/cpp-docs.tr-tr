---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
dev_langs:
- C++
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ea2a6d07a6664b74abaa1513a39f8f908f72fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389692"
---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
İç CRT işlevi. Geçerli veya belirtilen yerel ayar için birden çok baytlı karakter bayt sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int ___mb_cur_max_func(void);  
int ___mb_cur_max_l_func(_locale_t locale);  
int * __p___mb_cur_max(void);  
#define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### <a name="parameters"></a>Parametreler  
 locale  
 Sonuç almak için yerel ayar yapısı. Bu değer null ise, geçerli iş parçacığı yerel ayar kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli iş parçacığı yerel ayarı veya belirtilen bölge için birden çok baytlı karakter bayt sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu CRT geçerli değerini almak için kullandığı, dahili bir işlevdir [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) iş parçacığı yerel depolama biriminden makrosu. Kullanmanızı öneririz `MB_CUR_MAX` makrosu kodunuzda taşınabilirlik için.  
  
 `__mb_cur_max` Makrosu çağırmak için uygun bir yoldur `___mb_cur_max_func()` işlevi. `__p___mb_cur_max` İşlevi Visual C++ 5.0 ve önceki sürümleriyle uyumluluk için tanımlanır.  
  
 İç CRT işlevleri uygulamaya özel ve her değiştirilebilir. Biz kodunuzda bunların kullanılması önerilmez.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<CType.h >, \<stdlib.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)