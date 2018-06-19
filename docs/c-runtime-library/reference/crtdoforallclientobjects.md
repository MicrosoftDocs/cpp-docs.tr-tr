---
title: _CrtDoForAllClientObjects | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 889c3c4060098927df08d785e85b64e7e7becc2c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397206"
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Bir uygulama tarafından sağlanan işlev için tüm çağrılar **_clıent_block** (yalnızca hata ayıklama sürümü) yığınındaki türler.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parametreler

*pfn* işaretçi uygulama tarafından sağlanan işlev geri çağırma işlevi. Bu işlevi ilk parametresi verileri işaret eder. İkinci parametre çağrısına iletilen bağlam işaretçidir **_CrtDoForAllClientObjects**.

*bağlam* uygulama tarafından sağlanan bağlamı uygulama tarafından sağlanan işleve yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**_CrtDoForAllClientObjects** işlevi arar öbek 's bağlantılı ile bellek blokları istemcinize **_clıent_block** türü ve çağrıları bu tür bir blok olduğunda uygulama tarafından sağlanan işlev bulundu. Bulunan blok ve *bağlamı* parametresi için uygulama tarafından sağlanan işlev bağımsız değişkenleri olarak geçirilir. Hata ayıklama sırasında bir uygulama belirli bir grup ayırmalarının açıkça debug belleği ayırmaya yığın işlevleri çağırma ve blokları atanması belirterek izleyebilirsiniz **_clıent_block** engelleme türü. Bu blokları ayrı olarak izlenir ve farklı sızıntısı algılama ve bellek durumu Raporlama sırasında bildirilir.

Varsa **_CRTDBG_ALLOC_MEM_DF** bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı açık değilse, **_CrtDoForAllClientObjects** hemen döndürür. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtDoForAllClientObjects** ön işleme sırasında kaldırılır.

Hakkında daha fazla bilgi için **_clıent_block** yazın ve diğer hata ayıklama işlevleri tarafından kullanılan bkz [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Varsa *pfn* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır **EINVAL** ve işlevi döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h >, \<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Debug Evrensel C çalışma zamanı kitaplıkları yalnızca sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
