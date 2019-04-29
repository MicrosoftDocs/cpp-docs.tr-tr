---
title: _findclose
ms.date: 11/04/2016
apiname:
- _findclose
apilocation:
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
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 29010f8a502d463eeb6ca98837a1b7dae9f5ae6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333761"
---
# <a name="findclose"></a>_findclose

Belirtilen arama tanıtıcı kapatır ve ilişkili kaynakları serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parametreler

*Tanıtıcı*<br/>
Önceki bir çağrı tarafından döndürülen arama tanıtıcı **_findfirst**.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_findclose** 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar **errno** için **ENOENT**, artık eşleşen dosyaları belirten bulunamadı.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findclose**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../../c-runtime-library/system-calls.md)<br/>
[fileName İşlevleri Ara](../../c-runtime-library/filename-search-functions.md)<br/>
