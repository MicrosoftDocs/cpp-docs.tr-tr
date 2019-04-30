---
title: _CrtSetReportHook
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 7dcb916ea920751618ffa6a4afbcde8df5e35cba
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343041"
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

Bir istemci tanımlı raporlama işlevi, C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) takma tarafından yükler.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>Parametreler

*reportHook*<br/>
C çalışma zamanı içinde bağlama için yeni istemci tanımlı raporlama işlevi, raporlama işlemi hata ayıklayın.

## <a name="return-value"></a>Dönüş Değeri

Önceki istemci tanımlı raporlama işlevi döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportHook** raporlama sürecini C çalışma zamanı hata ayıklama kitaplığa kendi Raporlama işlevini kullanmak uygulamaya izin verir. Sonuç olarak, her [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) çağrılır hata ayıklama raporu oluşturmak için uygulama çağrıldığında ilk raporlama kullanıcının. Bir uygulama, hata ayıklama raporlarını filtreleme yapabilir veya spesifik ayırma türleri üzerinde odaklanın kullanarak hedeflere kullanılamıyor rapor gönderme gibi işlemleri gerçekleştirmek bu işlevi etkinleştirir **_CrtDbgReport**. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetReportHook** ön işleme sırasında kaldırılır.

Daha güçlü bir sürümü için **_CrtSetReportHook**, bkz: [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

**_CrtSetReportHook** işlevi yükler yeni istemci tanımlı raporlama işlevi, belirtilen *reportHook* ve önceki istemci tanımlı kanca döndürür. Aşağıdaki örnek, bir rapor istemci tanımlı kanca nasıl prototipli olmalıdır gösterir:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Burada *reportType* hata ayıklama rapor türü (**_CRT_WARN**, **_CRT_ERROR**, veya **_CRT_ASSERT**), *ileti* rapora dahil edilmek üzere tam olarak oluşturulmuş hata ayıklama kullanıcı iletisi ve **returnValue** istemci tanımlı tarafından belirtilen değere raporlama tarafından döndürülmesi gereken işlevi **_ CrtDbgReport**. Kullanılabilir rapor türleri eksiksiz bir açıklaması için bkz: [_CrtSetReportMode](crtsetreportmode.md) işlevi.

Başka bir raporlama olmadan gereklidir, istemci tanımlı raporlama işlevi tamamen hata ayıklama yapılacak işler değilse işlev döndürmelidir **TRUE**. İşlevi döndüğünde **FALSE**, **_CrtDbgReport** rapor türü, modu ve dosya için geçerli ayarları kullanarak hata ayıklama raporu oluşturmak için çağrılır. Belirterek buna **_CrtDbgReport** dönüş değerindeki **returnValue**, uygulama, aynı zamanda bir hata ayıklama kesmesini oluşup oluşmadığını denetleyebilir. Hata ayıklama raporunu nasıl yapılandırılan ve oluşturulan tam açıklaması için bkz. **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), ve **_CrtDbgReport**.

Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Uygulamanız ile derlenmişse **/CLR** ve uygulama çıkıldıktan sonra Raporlama işlevi ana çağrılır, herhangi bir CRT işlevleri Raporlama işlevini çağırırsa CLR bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
