---
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
ms.openlocfilehash: a7dd7d74992aeddffead1c6ef0d52cbc69848dad
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957281"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

DIŞI. CRT, bu iç işlevleri yalnızca ikili uyumluluğu koruyacak şekilde dışa aktarır.

## <a name="syntax"></a>Sözdizimi

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürülen değer önemli değil.

## <a name="remarks"></a>Açıklamalar

İç CRT işlevleri `___setlc_active_func` ve `___unguarded_readlc_active_add_func` artık kullanılmıyor olsa da, ikili uyumluluğu korumak için CRT kitaplığı tarafından verilir. Özgün amacı `___setlc_active_func` , `setlocale` işlevine Şu anda etkin olan çağrıların sayısını döndürmemelidir. Özgün amacı `___unguarded_readlc_active_add_func` , yerel ayara, kilitlemeden önce başvuruda bulunulan işlevlerin sayısını döndüramamıştı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|yok|

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
