---
description: 'Hakkında daha fazla bilgi edinin: _CrtCheckMemory'
title: _CrtCheckMemory
ms.date: 11/04/2016
api_name:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: f2537997a9adc1c2346560d3b65eecc633933616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221598"
---
# <a name="_crtcheckmemory"></a>_CrtCheckMemory

Hata ayıklama yığınında ayrılan bellek bloklarının bütünlüğünü onaylar (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Syntax

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_CRTCHECKMEMORY** true döndürür; Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtCheckMemory** işlevi, temeldeki temel yığını doğrulayarak ve her bellek bloğunu inceleyerek hata ayıklama yığın Yöneticisi tarafından ayrılan belleği doğrular. Temel alınan temel yığında bir hata veya bellek tutarsızlığına, hata ayıklama üstbilgi bilgilerine veya üzerine yazma arabelleklerine rastlıyorsanız, **_CrtCheckMemory** hata koşulunu açıklayan bilgiler içeren bir hata ayıklama raporu oluşturur. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtCheckMemory** çağrıları ön işleme sırasında kaldırılır.

**_CrtCheckMemory** davranışı, [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi kullanılarak [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının bit alanları ayarlanarak denetlenebilir. **_CRTDBG_CHECK_ALWAYS_DF** bit alanı, bir bellek ayırma işlemi istenilişinde, **_CrtCheckMemory** olarak çağrılır. Bu yöntem yürütmeyi yavaşlatır, ancak hataları hızlı bir şekilde yakalamak yararlı olur. **_CRTDBG_ALLOC_MEM_DF** bit alanı devre dışı bırakmak, **_CrtCheckMemory** yığının doğrulanmamasını ve hemen **doğru** dönmesini sağlar.

Bu işlev **true** veya **false** döndürdüğünden, basit bir hata ayıklama hata işleme mekanizması oluşturmak için [_assert](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, yığında bozulma algılanırsa bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

**_CrtCheckMemory** diğer hata ayıklama işlevleriyle nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek yönetimine ve hata ayıklama yığınına genel bakış için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtCheckMemory** kullanmanın bir örneği için bkz. [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
