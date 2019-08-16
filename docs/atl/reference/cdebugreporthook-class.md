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
ms.openlocfilehash: 7187448b2ba2c9d3ab0399aa3e75ce8d757bfec1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496767"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook sınıfı

Bir adlandırılmış kanala hata ayıklama raporları göndermek için bu sınıfı kullanın.

## <a name="syntax"></a>Sözdizimi

```
class CDebugReportHook
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDebugReportHook:: CDebugReportHook](#cdebugreporthook)|[Setpıename](#setpipename), [setTimeout](#settimeout)ve [SetHook](#sethook)çağırır.|
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|[CDebugReportHook:: RemoveHook](#removehook)çağırır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDebugReportHook:: CDebugReportHookProc](#cdebugreporthookproc)|Se C çalışma zamanı hata ayıklama raporlama işlemine bağlanan özel raporlama işlevi.|
|[CDebugReportHook:: RemoveHook](#removehook)|Adlandırılmış kanala hata ayıklama raporları gönderilmesini durdurmak ve önceki rapor kancasını geri yüklemek için bu yöntemi çağırın.|
|[CDebugReportHook:: SetHook](#sethook)|Adlandırılmış kanala hata ayıklama raporları göndermeye başlamak için bu yöntemi çağırın.|
|[CDebugReportHook:: Setpıename](#setpipename)|Hata ayıklama raporlarının gönderileceği kanalın makine ve adını ayarlamak için bu yöntemi çağırın.|
|[CDebugReportHook:: SetTimeout](#settimeout)|Bu sınıfın adlandırılmış kanalın kullanılabilir hale gelmesini bekleyeceği süreyi milisaniye olarak ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Hata ayıklama raporlarını bir adlandırılmış kanala göndermek için, hizmetlerinizin veya uygulamalarınızın hata ayıklama yapılarında bu sınıfın bir örneğini oluşturun. Hata ayıklama raporları [_Crtdbgreport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) çağırarak veya bu Işlev Için [atltrace](debugging-and-error-reporting-macros.md#atltrace) ve [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) makroları gibi bir sarmalayıcı kullanılarak oluşturulur.

Bu sınıfın kullanımı etkileşimli olmayan [pencere istasyonlarda](/windows/win32/winstation/window-stations)çalışan bileşenlere etkileşimli olarak hata ayıklamanıza olanak tanır.

Hata ayıklama raporlarının, iş parçacığının temel güvenlik bağlamı kullanılarak gönderildiğini unutmayın. Kimliğe bürünme geçici olarak devre dışı bırakılmıştır, böylece hata ayıklama raporlarının, Web uygulamalarında olduğu gibi düşük ayrıcalıklı kullanıcıların kimliğe bürünme durumunda görüntülenebilmesini sağlayabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

##  <a name="cdebugreporthook"></a>CDebugReportHook:: CDebugReportHook

[Setpıename](#setpipename), [setTimeout](#settimeout)ve [SetHook](#sethook)çağırır.

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıktısının gönderilmesi gereken makinenin adı. Yerel makinenin varsayılan değeri.

*Szpıename*<br/>
Hata ayıklama çıktısının gönderilmesi gereken adlandırılmış kanalın adı.

*dwTimeout*<br/>
Bu sınıfın adlandırılmış kanalın kullanılabilir hale gelmesi için bekleyeceği süre (milisaniye olarak).

##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook

[CDebugReportHook:: RemoveHook](#removehook)çağırır.

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>CDebugReportHook:: CDebugReportHookProc

C çalışma zamanı hata ayıklama raporlama işlemine bağlanan özel raporlama işlevi.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Raporun türü (_CRT_WARN, _CRT_ERROR veya _CRT_ASSERT).

*message*<br/>
İleti dizesi.

*returnValue*<br/>
[_Crtdbgreport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)tarafından döndürülmesi gereken değer.

### <a name="return-value"></a>Dönüş Değeri

Kanca, söz konusu iletiyi başka bir raporlama gerekli olmayacak şekilde tamamen işlediğinde yanlış döndürür. İletiyi normal şekilde `_CrtDbgReport` raporlemelidir, doğru değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Raporlama işlevi, adlandırılmış kanalı açmaya çalışır ve diğer uçtaki işlemle iletişim kurar. Kanal meşgulse, raporlama işlevi kanal boşalıncaya veya zaman aşımı süresi dolana kadar bekler. Zaman aşımı, Oluşturucu veya [CDebugReportHook:: setTimeout](#settimeout)çağrısıyla ayarlanabilir.

Bu işlevdeki kod, çağıran iş parçacığının temel güvenlik bağlamında yürütülür, diğer bir deyişle, kimliğe bürünme bu işlevin süresi boyunca devre dışı bırakılır.

##  <a name="removehook"></a>CDebugReportHook:: RemoveHook

Adlandırılmış kanala hata ayıklama raporları gönderilmesini durdurmak ve önceki rapor kancasını geri yüklemek için bu yöntemi çağırın.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>Açıklamalar

Önceki rapor kancasını geri yüklemek için [_Crtsetreporthook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) çağırır.

##  <a name="sethook"></a>CDebugReportHook:: SetHook

Adlandırılmış kanala hata ayıklama raporları göndermeye başlamak için bu yöntemi çağırın.

```
void SetHook() throw();
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama raporlarının [CDebugReportHookProc](#cdebugreporthookproc) aracılığıyla adlandırılan kanala yönlendirilmesini sağlamak Için [_Crtsetreporthook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) çağırır. Bu sınıf, [RemoveHook](#removehook) çağrıldığında geri yüklenebilmesi için önceki rapor kancasını izler.

##  <a name="setpipename"></a>CDebugReportHook:: Setpıename

Hata ayıklama raporlarının gönderileceği kanalın makine ve adını ayarlamak için bu yöntemi çağırın.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Parametreler

*szMachineName*<br/>
Hata ayıklama çıktısının gönderilmesi gereken makinenin adı.

*Szpıename*<br/>
Hata ayıklama çıktısının gönderilmesi gereken adlandırılmış kanalın adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="settimeout"></a>CDebugReportHook:: SetTimeout

Bu sınıfın adlandırılmış kanalın kullanılabilir hale gelmesini bekleyeceği süreyi milisaniye olarak ayarlamak için bu yöntemi çağırın.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Bu sınıfın adlandırılmış kanalın kullanılabilir hale gelmesi için bekleyeceği süre (milisaniye olarak).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
