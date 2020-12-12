---
description: 'Hakkında daha fazla bilgi edinin: _CrtDoForAllClientObjects'
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
api_name:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 73d2718aa4bfb68752a8424a385638a48aba2e36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319797"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Yığındaki tüm **_CLIENT_BLOCK** türleri için uygulama tarafından sağlanan bir işlev çağırır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parametreler

*PFN*<br/>
Uygulama tarafından sağlanan işlev geri çağırma işlevine yönelik işaretçi. Bu işlevin ilk parametresi, verileri işaret eder. İkinci parametre **_CrtDoForAllClientObjects** çağrısına geçirilen bağlam işaretçisidir.

*bağlam*<br/>
Uygulama tarafından sağlanan işleve geçirilecek uygulama tarafından sağlanan bağlam işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_CrtDoForAllClientObjects** işlevi, **_CLIENT_BLOCK** türündeki bellek blokları için yığının bağlantılı listesini arar ve bu türden bir blok bulunduğunda uygulama tarafından sağlanan işlevi çağırır. Bulunan blok ve *bağlam* parametresi, uygulama tarafından sağlanan işleve bağımsız değişken olarak geçirilir. Hata ayıklama sırasında bir uygulama, belleği ayırmak için hata ayıklama yığın işlevlerini açıkça çağırarak ve blokların **_CLIENT_BLOCK** blok türüne atandığını belirterek belirli bir ayırma grubunu izleyebilir. Bu bloklar daha sonra, sızıntı algılama ve bellek durumu raporlama sırasında ayrı olarak izlenebilir ve farklı şekilde raporlanır.

[_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının **_CRTDBG_ALLOC_MEM_DF** bit alanı açık değilse **_CrtDoForAllClientObjects** hemen döndürür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtDoForAllClientObjects** çağrıları ön işleme sırasında kaldırılır.

**_CLIENT_BLOCK** türü ve diğer hata ayıklama işlevleri tarafından nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

*PFN* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _Sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca evrensel C çalışma zamanı kitaplıklarının hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Yığın durumu raporlama Işlevleri](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
