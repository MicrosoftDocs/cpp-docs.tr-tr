---
description: 'Hakkında daha fazla bilgi edinin: _CrtMemCheckpoint'
title: _CrtMemCheckpoint
ms.date: 11/04/2016
api_name:
- _CrtMemCheckpoint
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: f7a88e63c99c063999f3de0d01e019fecd10496f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319683"
---
# <a name="_crtmemcheckpoint"></a>_CrtMemCheckpoint

Hata ayıklama yığınının geçerli durumunu alır ve uygulama tarafından sağlanan **_CrtMemState** yapısında depolar (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Bellek denetim noktası ile doldurulacak **_CrtMemState** yapısına yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemCheckpoint** işlevi, belirli bir anda hata ayıklama yığınının geçerli durumunun bir anlık görüntüsünü oluşturur. Bu anlık görüntü, bellek sızıntılarını ve diğer sorunları algılamaya yardımcı olmak üzere [_CrtMemDifference](crtmemdifference.md) gibi diğer yığın durum işlevleri tarafından kullanılabilir. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtMemState** çağrıları ön işleme sırasında kaldırılır.

Uygulama, *durum* parametresinde Crtdbg. h içinde tanımlanan **_CrtMemState** yapısının daha önce ayrılmış bir örneğine bir işaretçi iletmelidir. **_CrtMemCheckpoint** , denetim noktası oluşturma sırasında bir hatayla karşılaşırsa, bu, sorunu açıklayan bir **_CRT_WARN** hata ayıklama raporu oluşturur.

Yığın durumu işlevleri ve **_CrtMemState** yapısı hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

*Durum* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _Sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca UıCRT sürümlerini hata ayıkla.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
