---
title: _CrtMemCheckpoint | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1418278f4b6756db4e747162f090545c3e9f3ae
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107581"
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
