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
ms.openlocfilehash: 6ca83a9b9b48302e9ff4974d083d0a95796a1ef3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395519"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

Hata ayıklama yığınını geçerli durumunu alır ve depolar bir uygulama tarafından sağlanan içinde **_CrtMemState** yapısı (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumu* işaretçi **_CrtMemState** bellek denetim noktası doldurmak için yapısı.

## <a name="remarks"></a>Açıklamalar

**_CrtMemCheckpoint** işlev belirli bir anda hata ayıklama yığınını geçerli durumunda bir görüntüsünü oluşturur. Bu anlık görüntü diğer yığın durumu işlevler tarafından gibi kullanılabilir [_CrtMemDifference](crtmemdifference.md) bellek sızıntıları ve diğer sorunları saptamaya yardımcı olmak üzere. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemState** ön işleme sırasında kaldırılır.

Uygulama, önceden ayrılmış bir örneği için bir işaretçi geçmelidir **_CrtMemState** Crtdbg.h içinde tanımlanan yapısı *durumu* parametresi. Varsa **_CrtMemCheckpoint** karşılaştığı bir kontrol noktası oluşturulması sırasında hata işlevi oluşturur bir **_CRT_WARN** debug sorunu açıklayan bir rapor.

Yığın durumu İşlevler hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Varsa *durumu* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır **EINVAL** ve işlevi döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h >, \<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Debug UCRT yalnızca sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
