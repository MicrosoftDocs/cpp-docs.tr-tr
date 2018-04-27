---
title: _findclose | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89c1f515bb072c649a93b77e49b500ea4636e423
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="findclose"></a>_findclose

Belirtilen arama tanıtıcısı kapatır ve ilişkili kaynakları serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parametreler

*İşleme*<br/>
Önceki bir çağrı tarafından döndürülen arama tanıtıcısıyla **_findfirst**.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_findclose** 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar **errno** için **ENOENT**, daha fazla ile eşleşen dosyaları belirten bulunamadı.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findclose**|\<io.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../../c-runtime-library/system-calls.md)<br/>
[fileName İşlevleri Ara](../../c-runtime-library/filename-search-functions.md)<br/>
