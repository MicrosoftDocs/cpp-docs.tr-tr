---
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
ms.openlocfilehash: 7e458825a81b7032310458ccda52d9299e126a35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938869"
---
# <a name="_crtcheckmemory"></a>_CrtCheckMemory

Hata ayıklama yığınında ayrılan bellek bloklarının bütünlüğünü onaylar (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_Crtcheckmemory** doğru değerini döndürür; Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtcheckmemory** işlevi, temeldeki temel yığını doğrulayarak ve her bellek bloğunu inceleyerek hata ayıklama yığın Yöneticisi tarafından ayrılan belleği doğrular. Temel alınan temel yığında bir hata veya bellek tutarsızlığına, hata ayıklama üstbilgi bilgilerine veya üzerine yazma arabelleklerine rastlıyorsanız, **_Crtcheckmemory** , hata koşulunu açıklayan bilgiler içeren bir hata ayıklama raporu oluşturur. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtcheckmemory** çağrıları ön işleme sırasında kaldırılır.

**_Crtcheckmemory** davranışı, _Crtsetdbgflag Işlevi kullanılarak [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının bit alanları ayarlanarak denetlenebilir. [](crtsetdbgflag.md) **_Crtdbg_check_always_df** bit alanını, bellek ayırma işlemi Istenilişinde **_Crtcheckmemory** ile sonuçlanıyor. Bu yöntem yürütmeyi yavaşlatır, ancak hataları hızlı bir şekilde yakalamak yararlı olur. **_Crtdbg_alloc_mem_df** BIT alanı kapanmasının açılması, **_Crtcheckmemory** 'ın yığını doğrulaması ve hemen **doğru**dönmesini sağlar.

Bu işlev **true** veya **false**döndürdüğünden, basit bir hata ayıklama hata Işleme mekanizması oluşturmak için [_onaylama](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, yığında bozulma algılanırsa bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

**_Crtcheckmemory** 'ın diğer hata ayıklama işlevleriyle nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek yönetimine ve hata ayıklama yığınına genel bakış için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtCheckMemory**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_Crtcheckmemory**kullanımına ilişkin bir örnek için bkz. [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
