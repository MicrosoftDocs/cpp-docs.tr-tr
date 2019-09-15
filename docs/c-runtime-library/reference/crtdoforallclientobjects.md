---
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
ms.openlocfilehash: 4626df0db1956efd26ee267cb8cacf8ea4a4570c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942524"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Yığındaki tüm **_Client_block** türleri için uygulama tarafından sağlanan bir işlev çağırır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parametreler

*PFN*<br/>
Uygulama tarafından sağlanan işlev geri çağırma işlevine yönelik işaretçi. Bu işlevin ilk parametresi, verileri işaret eder. İkinci parametre, **_Crtdoforallclientobjects**çağrısına geçirilen bağlam işaretçisidir.

*bağlam*<br/>
Uygulama tarafından sağlanan işleve geçirilecek uygulama tarafından sağlanan bağlam işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_Crtdoforallclientobjects** işlevi, yığının bağlantılı listesinde **_Client_block** türüyle bellek blokları arar ve bu türden bir blok bulunduğunda uygulama tarafından sağlanan işlevi çağırır. Bulunan blok ve *bağlam* parametresi, uygulama tarafından sağlanan işleve bağımsız değişken olarak geçirilir. Hata ayıklama sırasında bir uygulama, belleği ayırmak için hata ayıklama yığın işlevlerini açıkça çağırarak ve blokların **_Client_block** blok türüne atanmasını belirterek belirli bir ayırma grubunu izleyebilir. Bu bloklar daha sonra, sızıntı algılama ve bellek durumu raporlama sırasında ayrı olarak izlenebilir ve farklı şekilde raporlanır.

[_Crtdbgflag](../../c-runtime-library/crtdbgflag.md) bayrağının **_Crtdbg_alloc_mem_df** bit alanı açık değilse, **_Crtdoforallclientobjects** hemen döndürülür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtdoforallclientobjects** çağrıları ön işleme sırasında kaldırılır.

**_Client_block** türü ve diğer hata ayıklama işlevleri tarafından nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

*PFN* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<Crtdbg. h >, \<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** Yalnızca evrensel C çalışma zamanı kitaplıklarının hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Yığın durumu raporlama Işlevleri](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
