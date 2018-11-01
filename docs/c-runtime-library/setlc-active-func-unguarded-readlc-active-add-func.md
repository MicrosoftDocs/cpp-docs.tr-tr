---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func
ms.date: 11/04/2016
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 23095bb13108ec9fde2b168035009f440e9d96f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525790"
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

ARTIK KULLANILMIYOR. CRT yalnızca ikili uyumluluğu korumak için bu iç işlevleri dışa aktarır.

## <a name="syntax"></a>Sözdizimi

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürülen değer önemli değildir.

## <a name="remarks"></a>Açıklamalar

Ancak iç CRT işlevleri `___setlc_active_func` ve `___unguarded_readlc_active_add_func` geçersiz ve artık kullanılmayan, bunlar ikili uyumluluğu korumak için CRT kitaplığı tarafından verilir. Özgün amacı `___setlc_active_func` etkin çağrı sayısı döndürülecek olan `setlocale` işlevi. Özgün amacı `___unguarded_readlc_active_add_func` kilitleme olmadan yerel başvurulan işlevler sayısını döndürmek için oluştu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|yok|

## <a name="see-also"></a>Ayrıca Bkz.

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)