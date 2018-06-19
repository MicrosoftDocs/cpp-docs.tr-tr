---
title: CRTThreadTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f08f0d6ea57aa5a153d190b357785911e64d6f09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358172"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits sınıfı
Bu sınıf için CRT iş parçacığı oluşturma işlevi sağlar. İş parçacığı CRT işlevleri kullanacaksanız bu sınıfı kullanın.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(Statik) CRT işlevleri kullanabileceğiniz bir iş parçacığı oluşturmak için bu işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı özellikleri belirli bir iş parçacığı türü için bir oluşturma işlevi sağlayan sınıflarıdır. Oluşturma işlevi Windows aynı imza ve semantiklerine sahip [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi.  
  
 İş parçacığı özellikleri aşağıdaki sınıflar tarafından kullanılır:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 İş parçacığı CRT işlevleri kullanmayan kullanırsanız [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="createthread"></a>  CRTThreadTraits::CreateThread  
 CRT işlevleri kullanabileceğiniz bir iş parçacığı oluşturmak için bu işlevini çağırın.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsa`  
 Yeni bir iş parçacığı için güvenlik öznitelikler.  
  
 `dwStackSize`  
 Yeni bir iş parçacığı için yığın boyutu.  
  
 `pfnThreadProc`  
 Yeni bir iş parçacığı iş parçacığı yordamı.  
  
 `pvParam`  
 İş parçacığı yordamı iletilecek parametre.  
  
 `dwCreationFlags`  
 Oluşturma (0 veya AfxBeginThread'e) işaretler.  
  
 `pdwThreadId`  
 [out] Adresi DWORD değişkenin, başarı, yeni oluşturulan iş parçacığı iş parçacığı kimliği alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanıtıcı hatası durumunda yeni oluşturulan iş parçacığı veya NULL döndürür. Çağrı [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) genişletilmiş hata bilgilerini için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) bu işlev parametreleri konusunda daha fazla bilgi.  
  
 Bu işlev çağrılarını [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) iş parçacığı oluşturulamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
