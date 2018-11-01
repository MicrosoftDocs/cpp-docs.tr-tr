---
title: _CrtCheckMemory
ms.date: 11/04/2016
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: cb39a76c140934dabdd1269c02aba6018691f917
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537156"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Hata ayıklama yığınındaki (yalnızca hata ayıklama sürümü) ayrılan bellek blokları bütünlüğünü doğrular.

## <a name="syntax"></a>Sözdizimi

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_CrtCheckMemory** TRUE; Aksi takdirde işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtCheckMemory** işlevi, temel alınan taban yığının doğrulanıyor ve her bellek bloğu incelemek hata ayıklama yığını Yöneticisi tarafından ayrılan bellek doğrular. Bir hata veya bellek tutarsızlık temel alınan taban yığının, hata ayıklama üst bilgi bilgileri veya üzerine yazma arabelleği karşılaşılırsa **_CrtCheckMemory** hata koşulu tanımlayan bilgileri içeren bir hata ayıklama raporunu oluşturur. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtCheckMemory** ön işleme sırasında kaldırılır.

Davranışını **_CrtCheckMemory** bit alanlarını ayarlayarak denetlenebilir [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) kullanarak bayrak [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi. Kapatma **_CRTDBG_CHECK_ALWAYS_DF** bit alanı üzerinde sonuçlarında **_CrtCheckMemory** bir bellek ayırma işlemi her istendiğinde çağrılıyor. Bu yöntem yürütme yavaşlatır, ancak hataları hızlı bir şekilde yakalamak için yararlıdır. Kapatma **_CRTDBG_ALLOC_MEM_DF** bit alanı OFF nedenleri **_CrtCheckMemory** değil yığın doğrulayın ve hemen döndürmek için **TRUE**.

Bu işlev döndürdüğü için **TRUE** veya **FALSE**, onu birine geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları basit bir hata ayıklama hata işleme mekanizması oluşturmak için. Bozulma i öbeğe algılanırsa aşağıdaki örnekte, bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Hakkında daha fazla bilgi için **_CrtCheckMemory** diğer hata ayıklama işlevleri ile kullanılabilmesi için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek yönetimi ve hata ayıklama yığınındaki genel bakış için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_CrtCheckMemory**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
