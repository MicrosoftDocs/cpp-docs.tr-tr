---
description: 'Hakkında daha fazla bilgi edinin: _CrtSetReportHook'
title: _CrtSetReportHook
ms.date: 11/04/2016
api_name:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 1e99e17b3a245dfe78e5a0f7367e422f4dc97600
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342250"
---
# <a name="_crtsetreporthook"></a>_CrtSetReportHook

, C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) bağlanarak istemci tanımlı bir raporlama işlevi kurar.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>Parametreler

*reportHook*<br/>
C çalışma zamanı hata ayıklama raporlama işlemine bağlamak için yeni istemci tanımlı raporlama işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceki istemci tanımlı raporlama işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportHook** , bir uygulamanın kendi raporlama işlevini C çalışma zamanı hata ayıklama kitaplığı raporlama işleminde kullanmasına izin verir. Sonuç olarak, bir hata ayıklama raporu oluşturmak için [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) her çağrıldığında, önce uygulamanın raporlama işlevi çağırılır. Bu işlevsellik, bir uygulamanın hata ayıklama raporlarını filtreleme gibi işlemleri gerçekleştirmesini sağlar; böylece belirli bir ayırma türlerine odaklanabilir veya **_CrtDbgReport** kullanarak kullanılamayan hedeflere rapor gönderebilirsiniz. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtSetReportHook** çağrıları ön işleme sırasında kaldırılır.

**_CrtSetReportHook** daha sağlam bir sürümü için bkz. [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

**_CrtSetReportHook** Işlevi, *reporthook* içinde belirtilen yeni istemci tanımlı raporlama işlevini yüklüyor ve önceki istemci tanımlı kancayı döndürüyor. Aşağıdaki örnek, istemci tanımlı bir rapor kancasını prototip olarak yazmanız gerektiğini göstermektedir:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Burada *reportType* , hata ayıklama rapor türüdür (**_CRT_WARN**, **_CRT_ERROR** veya **_CRT_ASSERT**), *ileti* raporda yer almak için tam olarak birleştirilmiş hata ayıklama Kullanıcı iletisidir ve **returnValue** , **_CrtDbgReport** tarafından döndürülmesi gereken istemci tanımlı raporlama işlevi tarafından belirtilen değerdir. Kullanılabilir rapor türlerinin tamamı hakkında açıklama için [_CrtSetReportMode](crtsetreportmode.md) işlevine bakın.

İstemci tanımlı raporlama işlevi, hata ayıklama iletisini daha fazla raporlama gerekmeden tamamen işlediğinde, işlev **true** döndürmelidir. İşlev **false** döndürdüğünde, rapor türü, mod ve dosya için geçerli ayarları kullanarak hata ayıklama raporu oluşturmak için **_CrtDbgReport** çağırılır. Buna ek olarak, **_CrtDbgReport** dönüş değeri **dönüşte** belirtilerek, uygulama bir hata ayıklama kesmenin oluşup oluşmadığını da denetleyebilir. Hata ayıklama raporunun nasıl yapılandırıldığı ve oluşturulduğu hakkında ayrıntılı bir açıklama için bkz. **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md)ve **_CrtDbgReport**.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Uygulamanız **/clr** ile derlenirse ve raporlama işlevi uygulama Main 'den çıktıktan sonra çağrılırsa, raporlama işlevi HERHANGI bir CRT IŞLEVINI çağırırsa clr bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
