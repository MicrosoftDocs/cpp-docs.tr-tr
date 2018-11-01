---
title: _CrtMemDifference
ms.date: 11/04/2016
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: f2c6306bf604737d0ace142674b21845a08e2dee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429659"
---
# <a name="crtmemdifference"></a>_CrtMemDifference

İki bellek karşılaştırır, durumları ve aralarındaki farkları (yalnızca hata ayıklama sürümü) döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Parametreler

*stateDiff*<br/>
İşaretçi bir **_CrtMemState** iki bellek durumu (döndürülen) arasındaki farklılıkları depolamak için kullanılan yapısı.

*Eski*<br/>
Önceki bir bellek durumuna yönelik işaretçi (**_CrtMemState** yapısı).

*Durum*<br/>
Sonraki bir bellek durumuna yönelik işaretçi (**_CrtMemState** yapısı).

## <a name="return-value"></a>Dönüş Değeri

Önemli ölçüde farklıysa, bellek durumları **_CrtMemDifference** TRUE döndürür. Aksi takdirde işlev false değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDifference** işlev karşılaştırır *eski* ve *durum* ve bunların farklılıkları depolar *stateDiff*, ardından da kullanabilirsiniz bellek sızıntıları ve diğer bellek sorunlarını algılamak için uygulama tarafından kullanılıyor. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemDifference** ön işleme sırasında kaldırılır.

*Durum* ve *eski* her bir geçerli işaretçi olması gereken bir **_CrtMemState** yapısı ile doldurulmuştur Crtdbg.h, tanımlanan [_CrtMemCheckpoint](crtmemcheckpoint.md)çağırmadan önce **_CrtMemDifference**. *stateDiff* daha önce ayrılmış bir örneğine bir işaretçi olmalıdır **_CrtMemState** yapısı. Varsa *stateDiff*, *durum*, veya *eski* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır **EINVAL** ve işlev false değerini döndürür.

**_CrtMemDifference** karşılaştırır **_CrtMemState** alanı bloklarında değerlerini *eski* bulunanlar *durum* ve sonuçta depolar*stateDiff*. Blok türü sayısı ayrılan ya da her tür için ayrılan bloğu sayısı iki bellek durumu arasında farklılık durumları önemli ölçüde farklı olduğu söylenir. İki durum da depolanan için hiç olmadığı kadar aynı anda iki durum ve toplam miktar arasındaki fark için ayrılan en büyük miktar arasındaki fark *stateDiff*.

Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek durumu işlemlerinde dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, açmak için kullanılabilir **_CRTDBG_CHECK_CRT_DF** , bit **_crtDbgFlag** bu blokları sızıntı algılama ve diğer bellek durumu dahil edilecek işlemler. Bırakılmış bellek blokları (**_FREE_BLOCK**) neden olmaz **_CrtMemDifference** TRUE döndürmek için.

Yığın durumu işlevleri hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
