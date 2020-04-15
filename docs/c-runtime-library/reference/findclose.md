---
title: _findclose
ms.date: 4/2/2020
api_name:
- _findclose
- _o__findclose
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: ed17963dc7331962c3ac0d522db2843822ec5f79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346791"
---
# <a name="_findclose"></a>_findclose

Belirtilen arama tanıtıcısını kapatır ve ilişkili kaynakları serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parametreler

*Işlemek*<br/>
**_findfirst**için önceki bir arama tarafından döndürülen arama tanıtıcısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_findclose** 0 döndürür. Aksi takdirde, -1 döndürür ve **ENOENT** **için errno** ayarlar , daha fazla eşleşen dosyaları bulunamadı belirten.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Aramaları](../../c-runtime-library/system-calls.md)<br/>
[Dosya Adı Arama Fonksiyonları](../../c-runtime-library/filename-search-functions.md)<br/>
