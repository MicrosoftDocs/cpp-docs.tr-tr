---
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
ms.openlocfilehash: edf91cd8c76fd080326e2e5eeac98f7f81ab90cf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942360"
---
# <a name="_crtmemcheckpoint"></a>_CrtMemCheckpoint

Hata ayıklama yığınının geçerli durumunu alır ve uygulama tarafından sağlanan **_Crtmemstate** yapısında depolar (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Bellek denetim noktası ile doldurulacak **_Crtmemstate** yapısına yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**_Crtmemcheckpoint** işlevi, belirli bir anda hata ayıklama yığınının geçerli durumunun bir anlık görüntüsünü oluşturur. Bu anlık görüntü, bellek sızıntılarını ve diğer sorunları algılamaya yardımcı olması için [_Crtmemdifference](crtmemdifference.md) gibi diğer yığın durum işlevleri tarafından kullanılabilir. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtmemstate** çağrıları ön işleme sırasında kaldırılır.

Uygulama, *durum* parametresinde Crtdbg. h Içinde tanımlanan **_Crtmemstate** yapısının önceden ayrılmış örneğine bir işaretçi iletmelidir. **_Crtmemcheckpoint** , denetim noktası oluşturma sırasında bir hatayla karşılaştığında, işlev sorunu açıklayan bir **_CRT_WARN** hata ayıklama raporu oluşturur.

Yığın durumu işlevleri ve **_Crtmemstate** yapısı hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

*Durum* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<Crtdbg. h >, \<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** Yalnızca UıCRT sürümlerini hata ayıkla.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
