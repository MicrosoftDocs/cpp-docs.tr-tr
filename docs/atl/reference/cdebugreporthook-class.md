---
title: CDebugReportHook Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: 8380556bbe007326156bf0ec0eefc23052e8e056
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747727"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook Sınıfı

Adlandırılmış bir boruya hata ayıklama raporları göndermek için bu sınıfı kullanın.

## <a name="syntax"></a>Sözdizimi

```
class CDebugReportHook
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|[SetPipeName,](#setpipename) [SetTimeout](#settimeout)ve [SetHook'u](#sethook)çağırır.|
|[CDebugReportHook::~CDebugReportHook](#dtor)|[CDebugReportHook çağırır::RemoveHook](#removehook).|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statik) C çalışma zamanı hata ayıklama raporlama işlemine bağlanan özel raporlama işlevi.|
|[CDebugReportHook::RemoveHook](#removehook)|Adlandırılmış pipe'ye hata ayıklama raporları göndermeyi durdurmak ve önceki rapor kancasını geri yüklemek için bu yöntemi arayın.|
|[CDebugReportHook::SetHook](#sethook)|Adlandırılmış boruya hata ayıklama raporları göndermeye başlamak için bu yöntemi arayın.|
|[CDebugReportHook::SetPipeName](#setpipename)|Hata ayıklama raporlarının göndereceği makineyi ve borunun adını ayarlamak için bu yöntemi arayın.|
|[CDebugReportHook::SetTimeout](#settimeout)|Bu sınıfın adlandırılmış borunun kullanılabilir olmasını bekleyeceği milisaniye cinsinden zamanı ayarlamak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Adlandırılmış bir boş¶neme raporları göndermek için hizmet veya uygulamalarınızın hata ayıklama yapılarında bu sınıfın bir örneğini oluşturun. Hata ayıklama [raporları, _CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) çağırarak veya [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) ve [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) makroları gibi bu işlev için bir sarmalayıcı kullanılarak oluşturulur.

Bu sınıfın kullanımı etkileşimli olmayan [pencere istasyonlarında](/windows/win32/winstation/window-stations)çalışan bileşenleri devre dışı hata ayıklama sağlar.

Hata ayıklama raporlarının iş parçacığının temel güvenlik bağlamı kullanılarak gönderildiğini unutmayın. Web uygulamaları gibi düşük ayrıcalıklı kullanıcıların kimliğe bürünme gerçekleştiği durumlarda hata ayıklama raporlarının görüntülenebileceği için kimliğe bürünme geçici olarak devre dışı bırakılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook

[SetPipeName,](#setpipename) [SetTimeout](#settimeout)ve [SetHook'u](#sethook)çağırır.

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıkışının gönderilmesi gereken makinenin adı. Varsayılan olarak yerel makine için.

*szPipeName*<br/>
Hata ayıklama çıkışının gönderilmesi gereken adlandırılmış borunun adı.

*dwTimeout*<br/>
Bu sınıfın adlandırılmış borunun kullanılabilir olmasını bekleyeceği milisaniye cinsinden süre.

## <a name="cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>CDebugReportHook::~CDebugReportHook

[CDebugReportHook çağırır::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

## <a name="cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc

C çalışma zamanı hata ayıklama raporlama işlemine bağlanan özel raporlama işlevi.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Parametreler

*Reporttype*<br/>
Raporun türü (_CRT_WARN, _CRT_ERROR veya _CRT_ASSERT).

*İleti*<br/>
İleti dizesi.

*Returnvalue*<br/>
[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)tarafından döndürülmesi gereken değer.

### <a name="return-value"></a>Dönüş Değeri

Kanca, söz konusu iletiyi tamamen işlerse, başka bir raporlama gerektirmemesi için FALSE'u döndürür. İletiyi `_CrtDbgReport` normal şekilde bildirmesi gerekiyorsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Raporlama işlevi, adlandırılmış boruyu açmaya ve diğer uçtaki işlemle iletişim kurmaya çalışır. Boru meşgulse, raporlama işlevi boru boşalana veya zaman aşımı süresi dolana kadar bekler. Zaman acısı oluşturucu veya [CDebugReportHook::SetTimeout](#settimeout)için bir çağrı tarafından ayarlanabilir.

Bu işlevdeki kod, arama iş parçacığının temel güvenlik bağlamında yürütülür, diğer bir deyişle, kimliğe bürünme bu işlev süresince devre dışı bırakılır.

## <a name="cdebugreporthookremovehook"></a><a name="removehook"></a>CDebugReportHook::RemoveHook

Adlandırılmış pipe'ye hata ayıklama raporları göndermeyi durdurmak ve önceki rapor kancasını geri yüklemek için bu yöntemi arayın.

```cpp
void RemoveHook() throw();
```

### <a name="remarks"></a>Açıklamalar

Önceki rapor kancasını geri yüklemek için [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) çağırır.

## <a name="cdebugreporthooksethook"></a><a name="sethook"></a>CDebugReportHook::SetHook

Adlandırılmış boruya hata ayıklama raporları göndermeye başlamak için bu yöntemi arayın.

```cpp
void SetHook() throw();
```

### <a name="remarks"></a>Açıklamalar

[CDebugReportHookProc](#cdebugreporthookproc) üzerinden adlandırılmış boruya yönlendirilen hata ayıklama raporlarının [_CrtSetReportHook2.](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) Bu sınıf, [RemoveHook](#removehook) çağrıldığında geri yüklenebilmeleri için önceki rapor kancasını izler.

## <a name="cdebugreporthooksetpipename"></a><a name="setpipename"></a>CDebugReportHook::SetPipeName

Hata ayıklama raporlarının göndereceği makineyi ve borunun adını ayarlamak için bu yöntemi arayın.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıkışının gönderilmesi gereken makinenin adı.

*szPipeName*<br/>
Hata ayıklama çıkışının gönderilmesi gereken adlandırılmış borunun adı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="cdebugreporthooksettimeout"></a><a name="settimeout"></a>CDebugReportHook::SetTimeout

Bu sınıfın adlandırılmış borunun kullanılabilir olmasını bekleyeceği milisaniye cinsinden zamanı ayarlamak için bu yöntemi arayın.

```cpp
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Bu sınıfın adlandırılmış borunun kullanılabilir olmasını bekleyeceği milisaniye cinsinden süre.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
