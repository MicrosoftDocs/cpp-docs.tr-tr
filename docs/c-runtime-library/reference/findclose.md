---
title: _findclose
ms.date: 11/04/2016
api_name:
- _findclose
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
ms.openlocfilehash: c67336cc12bcdee754edd40b91078faa83a17984
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957329"
---
# <a name="_findclose"></a>_findclose

Belirtilen arama tutamacını kapatır ve ilişkili kaynakları yayınlar.

## <a name="syntax"></a>Sözdizimi

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parametreler

*tutamaçlardan*<br/>
Önceki **_findcall**çağrısı tarafından döndürülen arama tanıtıcısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa **_findclose** 0 döndürür. Aksi takdirde,-1 döndürür ve **errno** , daha fazla eşleşen dosya bulunamadığını **belirten olarak ayarlar**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findclose**|\<GÇ. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../../c-runtime-library/system-calls.md)<br/>
[fileName İşlevleri Ara](../../c-runtime-library/filename-search-functions.md)<br/>
