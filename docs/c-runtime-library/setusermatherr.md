---
description: 'Hakkında daha fazla bilgi edinin: __setusermatherr'
title: __setusermatherr
ms.date: 11/04/2016
api_name:
- __setusermatherr
api_location:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __setusermatherr
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
ms.openlocfilehash: 11b470f3c39a22b212187936dc4bad36c3cefd1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277094"
---
# <a name="__setusermatherr"></a>__setusermatherr

[_Matherr](../c-runtime-library/reference/matherr.md) yordamı yerine matematik hatalarını işlemek için Kullanıcı tarafından sağlanan bir rountine belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
void __setusermatherr(
   _HANDLE_MATH_ERROR pf
   )
```

#### <a name="parameters"></a>Parametreler

*PF*<br/>
Kullanıcı tarafından sağlanan bir uygulamaya yönelik işaretçi `_matherr` .

*PF* parametresinin türü olarak bildirilmiştir `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` .

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__setusermatherr|matherr. c|
