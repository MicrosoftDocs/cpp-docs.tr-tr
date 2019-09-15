---
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
ms.openlocfilehash: 77c1e499c66a76027e872783e256754ef72e465d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938508"
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

**_Crtsetreporthook** , bir uygulamanın kendi raporlama işlevini C çalışma zamanı hata ayıklama kitaplığı raporlama işleminde kullanmasına izin verir. Sonuç olarak, hata ayıklama raporu oluşturmak için [_Crtdbgreport](crtdbgreport-crtdbgreportw.md) çağrıldığında, önce uygulamanın raporlama işlevi çağırılır. Bu işlevsellik, bir uygulamanın hata ayıklama raporlarını filtreleme gibi işlemleri gerçekleştirmesini sağlar; böylece belirli bir ayırma türlerine odaklanabilir veya **_Crtdbgreport**kullanılarak kullanılamayan hedeflere bir rapor gönderebilirsiniz. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtsetreporthook** çağrıları ön işleme sırasında kaldırılır.

**_Crtsetreporthook**'in daha sağlam bir sürümü için bkz. [_Crtsetreporthook2](crtsetreporthook2-crtsetreporthookw2.md).

**_Crtsetreporthook** Işlevi, *reporthook* içinde belirtilen yeni istemci tanımlı raporlama işlevini yüklüyor ve önceki istemci tanımlı kancayı döndürüyor. Aşağıdaki örnek, istemci tanımlı bir rapor kancasını prototip olarak yazmanız gerektiğini göstermektedir:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Burada *reportType* , hata ayıklama rapor türüdür ( **_CRT_WARN**, **_CRT_ERROR**veya **_CRT_ASSERT**), *ileti* raporda yer almak için tam olarak birleştirilmiş hata ayıklama Kullanıcı iletisidir ve **returnValue** değeridir **_Crtdbgreport**tarafından döndürülmesi gereken istemci tanımlı raporlama işlevi tarafından belirtilir. Kullanılabilir rapor türlerinin tamamen açıklaması için, bkz. [_Crtsetreportmode](crtsetreportmode.md) işlevi.

İstemci tanımlı raporlama işlevi, hata ayıklama iletisini daha fazla raporlama gerekmeden tamamen işlediğinde, işlev **true**döndürmelidir. İşlev **false**döndürdüğünde, rapor türü, mod ve dosya için geçerli ayarları kullanarak hata ayıklama raporu oluşturmak için **_CrtDbgReport** çağırılır. Ayrıca, uygulama, **_Crtdbgreport** Return değerini **returnValue**olarak belirterek, bir hata ayıklama kesmenin oluşup oluşmadığını da denetleyebilir. Hata ayıklama raporunun nasıl yapılandırıldığı ve oluşturulduğu hakkında açıklayıcı bir açıklama için, bkz. **_Crtsetreportmode**, [_CrtSetReportFile](crtsetreportfile.md)ve **_CrtDbgReport**.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Uygulamanız **/clr** ile derlenirse ve raporlama işlevi uygulama Main 'den çıktıktan sonra çağrılırsa, raporlama işlevi HERHANGI bir CRT IŞLEVINI çağırırsa clr bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetReportHook**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
