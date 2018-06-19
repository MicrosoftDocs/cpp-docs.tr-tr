---
title: _CrtCheckMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6d4b84fd717525e7206956964204794fe6b88c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396670"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Hata ayıklama yığınını (yalnızca hata ayıklama sürümü) ayrılan bellek blokları bütünlüğünü doğrular.

## <a name="syntax"></a>Sözdizimi

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_CrtCheckMemory** TRUE; Aksi takdirde işlevi FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtCheckMemory** işlevi temel temel yığın doğrulamak ve her bellek bloğu inceleyerek hata ayıklama yığını Yöneticisi tarafından ayrılan bellek doğrular. Bir hata veya bellek tutarsızlık temel temel öbek, hata ayıklama üst bilgileri veya üzerine yaz arabellekleri karşılaştıysanız **_CrtCheckMemory** hata koşulu tanımlayan bilgileri içeren bir hata ayıklama raporunu oluşturur. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtCheckMemory** ön işleme sırasında kaldırılır.

Davranışını **_CrtCheckMemory** bit alanlarını ayarlayarak denetlenebilir [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) kullanarak bayrak [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi. Kapatma **_CRTDBG_CHECK_ALWAYS_DF** bit alan ON sonuçlarında **_CrtCheckMemory** bir bellek ayırma işlemi her istendiğinde çağrılan. Bu yöntem yürütme yavaşlatır rağmen hataları hızla yakalamak için yararlıdır. Kapatma **_CRTDBG_ALLOC_MEM_DF** bit alan OFF nedenler **_CrtCheckMemory** değil öbek doğrulayın ve hemen dönmek için **doğru**.

Bu işlev döndürdüğünden **TRUE** veya **FALSE**, onu biri olarak geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Yığın bozulması algılanırsa, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Hakkında daha fazla bilgi için **_CrtCheckMemory** diğer hata ayıklama işlevleri ile kullanılabilmesi için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek yönetimi ve hata ayıklama yığınını genel bakış için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağına ilişkin bir örnek için **_CrtCheckMemory**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
