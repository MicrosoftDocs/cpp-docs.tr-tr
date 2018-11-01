---
title: CDebugReportHook sınıfı
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
ms.openlocfilehash: 370581effcd7233d0f1f474c80a273809be58551
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551495"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook sınıfı

Bu sınıf, hata ayıklama raporları bir adlandırılmış kanala göndermek için kullanın.

## <a name="syntax"></a>Sözdizimi

```
class CDebugReportHook
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Çağrıları [SetPipeName](#setpipename), [SetTimeout](#settimeout), ve [SetHook](#sethook).|
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Çağrıları [CDebugReportHook::RemoveHook](#removehook).|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statik) İşlem C çalışma zamanı hata ayıklama raporlama kancalandı özel raporlama işlev.|
|[CDebugReportHook::RemoveHook](#removehook)|Adlandırılmış kanal için hata ayıklama raporları gönderilmesini durdurmak için bu yöntemi çağırır ve önceki rapor kanca geri yükleyin.|
|[CDebugReportHook::SetHook](#sethook)|Adlandırılmış kanal için hata ayıklama raporlarını göndermeden başlatmak için bu yöntemi çağırın.|
|[CDebugReportHook::SetPipeName](#setpipename)|Makine ve hata ayıklama raporlarını gönderilecek kanal adını ayarlamak için bu yöntemi çağırın.|
|[CDebugReportHook::SetTimeout](#settimeout)|Bu sınıf adlandırılmış kanal kullanılabilir olmasını bekleyeceği milisaniye cinsinden süresi ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, hizmetlerin veya uygulamaların hata ayıklama raporları bir adlandırılmış kanala göndermek için bu sınıfın bir örneğini oluşturun. Hata ayıklama raporları oluşturulur çağırarak [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) veya bir sarmalayıcı gibi bu işlev için kullanarak [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) ve [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) makroları.

Bu sınıfın kullanımını etkileşimli olarak etkileşimli olmayan çalışan bileşenleri hatalarını ayıklamanızı sağlar [penceresi istasyonları](/windows/desktop/winstation/window-stations).

İş parçacığının temel güvenlik bağlamını kullanarak hata ayıklama raporlar gönderilir unutmayın. Burada düşük ayrıcalıklı kullanıcı kimliğe bürünme, gibi web uygulamalarında gerçekleşen durumlarda hata ayıklama raporlarının görüntülenebilmesi için kimliğe bürünme geçici olarak devre dışı bırakıldı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook

Çağrıları [SetPipeName](#setpipename), [SetTimeout](#settimeout), ve [SetHook](#sethook).

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıkışını gönderilmesi gereken makine adı. Varsayılan olarak yerel makine.

*szPipeName*<br/>
Hata ayıklama çıkışını gönderilmesi gereken bir adlandırılmış kanal adı.

*dwTimeout*<br/>
Bu sınıf, adlandırılmış kanal kullanılabilir olmasını bekleyeceği milisaniye cinsinden süre.

##  <a name="dtor"></a>  CDebugReportHook:: ~ CDebugReportHook

Çağrıları [CDebugReportHook::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc

İşlem C çalışma zamanı hata ayıklama raporlama kancalandı özel raporlama işlev.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor (_CRT_WARN, _CRT_ERROR veya _CRT_ASSERT) türü.

*message*<br/>
İleti dizesi.

*returnValue*<br/>
Tarafından döndürülen değer [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).

### <a name="return-value"></a>Dönüş Değeri

Daha fazla raporlama olmadan gereklidir kanca söz konusu iletiyi tamamen işleme, false değerini döndürür. Gerekirse TRUE döndürür `_CrtDbgReport` normal bir şekilde iletisi raporu vermesi.

### <a name="remarks"></a>Açıklamalar

Raporlama işlevi, adlandırılmış kanal açın ve diğer uçtaki işlemi ile iletişim kurmak çalışır. Kanal meşgul ise, raporlama işlevi boş bir kanaldır veya zaman aşımı süresi doluncaya kadar bekleyin. Zaman aşımı oluşturucu veya bir çağrı tarafından ayarlanabilir [CDebugReportHook::SetTimeout](#settimeout).

Bu işlev kodu çağıran iş parçacığını temel güvenlik bağlamında yürütülür, kimliğe bürünme süresi boyunca bu işlev, diğer bir deyişle, devre dışı bırakıldı.

##  <a name="removehook"></a>  CDebugReportHook::RemoveHook

Adlandırılmış kanal için hata ayıklama raporları gönderilmesini durdurmak için bu yöntemi çağırır ve önceki rapor kanca geri yükleyin.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) önceki rapor kanca geri yüklemek için.

##  <a name="sethook"></a>  CDebugReportHook::SetHook

Adlandırılmış kanal için hata ayıklama raporlarını göndermeden başlatmak için bu yöntemi çağırın.

```
void SetHook() throw();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) üzerinden hata ayıklama raporlar için [CDebugReportHookProc](#cdebugreporthookproc) adlandırılmış kanal için. Bu sınıf önceki rapor kanca olması için izler geri [RemoveHook](#removehook) çağrılır.

##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName

Makine ve hata ayıklama raporlarını gönderilecek kanal adını ayarlamak için bu yöntemi çağırın.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıkışını gönderilmesi gereken makine adı.

*szPipeName*<br/>
Hata ayıklama çıkışını gönderilmesi gereken bir adlandırılmış kanal adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout

Bu sınıf adlandırılmış kanal kullanılabilir olmasını bekleyeceği milisaniye cinsinden süresi ayarlamak için bu yöntemi çağırın.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Bu sınıf, adlandırılmış kanal kullanılabilir olmasını bekleyeceği milisaniye cinsinden süre.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
