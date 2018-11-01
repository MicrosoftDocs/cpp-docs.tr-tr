---
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 86268bd9ac49c8ea27f715404236bcb9291f5d8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521197"
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Tüm uygulama tarafından sağlanan bir işlevi çağırır **_clıent_block** (yalnızca hata ayıklama sürümü) yığınındaki türler.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parametreler

*pfn*<br/>
Uygulama tarafından sağlanan işlev geri çağırma işlevi işaretçisi. İlk parametre olarak bu işlev verileri gösterir. İkinci parametre çağrısına geçirilen içerik işaretçisidir **_CrtDoForAllClientObjects**.

*Bağlam*<br/>
Uygulama tarafından sağlanan bağlamı uygulama tarafından sağlanan işleve yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**_CrtDoForAllClientObjects** işlevi ile bellek blokları yığının bağlantılı liste arar **_clıent_block** türü ve çağrılarını bu tür bir blok, uygulama tarafından sağlanan işlev bulundu. Bulunan blok ve *bağlam* parametresi, uygulama tarafından sağlanan işlevine bağımsız değişken olarak geçirilir. Hata ayıklama sırasında bir uygulama belirli bir ayırma grubunu hata ayıklama yığın işlevleri bellek ayırmak için açıkça çağırmak ve blokları atanması belirterek izleyebilirsiniz **_clıent_block** blok türü. Bu blokları ayrı ayrı izlenir ve farklı sızıntı algılama ve bellek durumu bildiren sırasında bildirilir.

Varsa **_CRTDBG_ALLOC_MEM_DF** bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı açık değilse, **_CrtDoForAllClientObjects** hemen döndürür. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtDoForAllClientObjects** ön işleme sırasında kaldırılır.

Hakkında daha fazla bilgi için **_clıent_block** yazın ve diğer hata ayıklama işlevleri tarafından kullanılabilmesi için bkz [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Varsa *pfn* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır **EINVAL** ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h >, \<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** sürümleri, Evrensel C çalışma zamanı kitaplıklarının yalnızca hata ayıklama.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Öbek durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
