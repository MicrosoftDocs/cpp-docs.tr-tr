---
title: "CDebugReportHook sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs: C++
helpviewer_keywords: CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df098ee80bcd8fa81b5503cc21b08ded86945a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook sınıfı
Bu sınıf için bir adlandırılmış kanal hata ayıklama raporları göndermek için kullanın.  
  
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
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statik) İşlem raporlama C çalışma zamanı hata ayıklama sayfaya özel raporlama işlevi.|  
|[CDebugReportHook::RemoveHook](#removehook)|Adlandırılmış kanal hata ayıklama raporları göndermeyi durdurmak için bu yöntemi çağırın ve önceki rapor kanca geri yükleyin.|  
|[CDebugReportHook::SetHook](#sethook)|Adlandırılmış kanal hata ayıklama raporları gönderme başlatmak için bu yöntemi çağırın.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Hata ayıklama raporları gönderilecek kanal adını ve makine ayarlamak için bu yöntemi çağırın.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Bu sınıf adlandırılmış kanal kullanılabilir olmasını bekler milisaniye cinsinden süre ayarlamak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, hizmetlerin veya bir adlandırılmış kanal hata ayıklama raporları göndermek için uygulamalar bu sınıfının bir örneğini oluşturun. Hata ayıklama raporları oluşturulur çağırarak [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) veya bu işlev için sarmalayıcı gibi kullanılarak [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) ve [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) makroları.  
  
 Bu sınıf kullanılmasına izin verir, etkileşimli olarak etkileşimli olmayan çalışan bileşenleri hata ayıklamak [pencere istasyonları](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 İş parçacığı, temel alınan güvenlik bağlamı kullanarak hata ayıklama raporlar gönderilir unutmayın. Böylece burada düşük ayrıcalıklı kullanıcıların kimliğine bürünme yer, gibi web uygulamalarında aldığı durumlarda hata ayıklama raporlarının görüntülenebilmesi için kimliğe bürünme geçici olarak devre dışıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 Çağrıları [SetPipeName](#setpipename), [SetTimeout](#settimeout), ve [SetHook](#sethook).  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `szMachineName`  
 Hata ayıklama çıktısı gönderilmesi gereken makine adı. Varsayılan olarak yerel makine.  
  
 `szPipeName`  
 Hata ayıklama çıktısı gönderilmesi gerektiğini adlandırılmış kanal adı.  
  
 `dwTimeout`  
 Bu sınıf kullanılabilir hale gelmesi için adlandırılmış kanal bekleyeceği milisaniye cinsinden süre.  
  
##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 Çağrıları [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 İşlem raporlama C çalışma zamanı hata ayıklama sayfaya özel raporlama işlevi.  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `reportType`  
 Raporun (_CRT_WARN, _CRT_ERROR veya _CRT_ASSERT) türü.  
  
 `message`  
 İleti dizesi.  
  
 *returnValue*  
 Tarafından döndürülen değeri [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla raporlama yok gereklidir kanca söz konusu iletinin tamamen işleme ise false değerini döndürür. TRUE değeri döndürür, `_CrtDbgReport` ileti normal şekilde bildirmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Adlandırılmış kanal açın ve diğer uçtaki işlemi ile iletişim kurmak raporlama işlevi çalışır. Kanal meşgulse raporlama işlevi boş bir kanaldır veya zaman aşımı süresi doluncaya kadar bekler. Zaman aşımı Oluşturucusu veya yapılan bir çağrı tarafından ayarlanabilir [CDebugReportHook::SetTimeout](#settimeout).  
  
 Bu işlevde kod, çağıran iş parçacığı temel güvenlik bağlamında yürütülür, kimliğe bürünme boyunca bu işlevi başka bir deyişle, devre dışı bırakıldı.  
  
##  <a name="removehook"></a>CDebugReportHook::RemoveHook  
 Adlandırılmış kanal hata ayıklama raporları göndermeyi durdurmak için bu yöntemi çağırın ve önceki rapor kanca geri yükleyin.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) önceki rapor kanca geri yüklemek için.  
  
##  <a name="sethook"></a>CDebugReportHook::SetHook  
 Adlandırılmış kanal hata ayıklama raporları gönderme başlatmak için bu yöntemi çağırın.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) aracılığıyla yönlendirilen hata ayıklama rapor [CDebugReportHookProc](#cdebugreporthookproc) adlandırılmış kanalına. Bu sınıf önceki rapor kanca olması için izler geri [RemoveHook](#removehook) olarak adlandırılır.  
  
##  <a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Hata ayıklama raporları gönderilecek kanal adını ve makine ayarlamak için bu yöntemi çağırın.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `szMachineName`  
 Hata ayıklama çıktısı gönderilmesi gereken makine adı.  
  
 `szPipeName`  
 Hata ayıklama çıktısı gönderilmesi gerektiğini adlandırılmış kanal adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Bu sınıf adlandırılmış kanal kullanılabilir olmasını bekler milisaniye cinsinden süre ayarlamak için bu yöntemi çağırın.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwTimeout`  
 Bu sınıf kullanılabilir hale gelmesi için adlandırılmış kanal bekleyeceği milisaniye cinsinden süre.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../atl/reference/atl-classes.md)
