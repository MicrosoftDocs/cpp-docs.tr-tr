---
description: 'Hakkında daha fazla bilgi edinin: ___setlc_active_func ___unguarded_readlc_active_add_func'
title: ___setlc_active_func, ___unguarded_readlc_active_add_func
ms.date: 11/04/2016
api_name:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 85273b52102e9cca2e42ba4401da60b1d292560c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277095"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

Dışı. CRT, bu iç işlevleri yalnızca ikili uyumluluğu koruyacak şekilde dışa aktarır.

## <a name="syntax"></a>Syntax

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürülen değer önemli değil.

## <a name="remarks"></a>Açıklamalar

İç CRT işlevleri `___setlc_active_func` ve `___unguarded_readlc_active_add_func` artık kullanılmıyor olsa da, ikili uyumluluğu korumak için CRT kitaplığı tarafından verilir. Özgün amacı, `___setlc_active_func` işlevine Şu anda etkin olan çağrıların sayısını döndürmemelidir `setlocale` . Özgün amacı, `___unguarded_readlc_active_add_func` yerel ayara, kilitlemeden önce başvuruda bulunulan işlevlerin sayısını döndüramamıştı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|yok|

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
