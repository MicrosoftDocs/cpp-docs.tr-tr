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
ms.openlocfilehash: 7eb9682a648f8e302a620e3c2e0dc1631abf7945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068279"
---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

İç CRT işlevi. Çok baytlı bir karakterin geçerli ya da belirtilen yerel ayar için bayt maksimum sayısını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Parametreler

Yerel sonuç almak için yerel ayar yapısı. Bu değer null ise, geçerli iş parçacığı yerel ayarı kullanılır.

## <a name="return-value"></a>Dönüş Değeri

Çok baytlı bir karakterin geçerli iş parçacığı yerel ayarı veya belirtilen yerel bayt sayısı.

## <a name="remarks"></a>Açıklamalar

Geçerli değerini almak için CRT kullanan bir iç işlev budur [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) iş parçacığı yerel depolama alanından makrosu. Kullanmanızı öneririz `MB_CUR_MAX` makro kod taşınabilir.

`__mb_cur_max` Makrodur çağırmak için kullanışlı bir yol `___mb_cur_max_func()` işlevi. `__p___mb_cur_max` İşlevi, Visual C++ 5.0 ve önceki sürümleriyle uyumluluk için tanımlanır.

İç CRT işlevleri uygulamasına özgüdür ve her değişebilir bırakın. Kodunuzda bunların kullanılması önerilmemektedir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<CType.h >, \<stdlib.h >|

## <a name="see-also"></a>Ayrıca Bkz.

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)