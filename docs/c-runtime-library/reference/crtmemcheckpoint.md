---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
apiname:
- _CrtMemCheckpoint
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
apitype: DLLExport
f1_keywords:
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: ee435ba3e9e40795280dee0f97feaad32c8b0fc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589523"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

Hata ayıklama yığınındaki geçerli durumunu alır ve depolayan bir uygulama tarafından sağlanan **_CrtMemState** yapısı (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
İşaretçi **_CrtMemState** bellek denetim noktasıyla doldurmak üzere yapısı.

## <a name="remarks"></a>Açıklamalar

**_CrtMemCheckpoint** işlevi, belirli bir andaki hata ayıklama yığınının geçerli durumu anlık görüntüsünü oluşturur. Bu anlık görüntü diğer yığın durumu işlevleri tarafından gibi kullanılabilir [_CrtMemDifference](crtmemdifference.md) bellek sızıntıları ve diğer sorunların algılanmasına yardımcı olmak için. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemState** ön işleme sırasında kaldırılır.

Uygulama, daha önce ayrılmış bir örneğine bir işaretçi geçmelidir **_CrtMemState** yapısı, Crtdbg.h, tanımlanan *durumu* parametresi. Varsa **_CrtMemCheckpoint** denetim noktası oluşturma sırasında bir hatayla karşılaşıyorsa, işlev oluşturur bir **_CRT_WARN** hata ayıklama sorunu açıklayan bir rapor.

Yığın durumu işlevleri hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Varsa *durumu* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır **EINVAL** ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h >, \<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata giderme yalnızca UCRT sürümü.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
