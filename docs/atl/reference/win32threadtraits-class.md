---
title: Win32ThreadTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c61ba91fe29610f4b313cf31c65f514ef8e46f96
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883680"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits sınıfı
Bu sınıf için bir Windows iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanmayacaksa kullanın.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Statik) CRT işlevlerinin kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı nitelikler iş parçacığı belirli bir tür için bir oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi aynı imza ve semantiğine sahip Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi.  
  
 İş parçacığı nitelikler aşağıdaki sınıflar tarafından kullanılır:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 İş parçacığı CRT işlevleri kullanacaksanız, kullanmak [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread  
 CRT işlevlerinin kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevi çağırın.  
  
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
 *lpsa*  
 Yeni iş parçacığı için güvenlik öznitelikleri.  
  
 *dwStackSize*  
 Yeni iş parçacığı için yığın boyutu.  
  
 *pfnThreadProc*  
 Yeni iş parçacığının iş parçacığı yordamı.  
  
 *pvParam*  
 İş parçacığı yordama iletilecek parametre.  
  
 *dwCreationFlags*  
 Oluşturma (0 veya CREATE_SUSPENDED) işaretler.  
  
 *pdwThreadId*  
 [out] Başarı durumunda, yeni oluşturulan iş parçacığının iş parçacığı kimliği alır, DWORD değişkenin adresidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanıtıcı, yeni oluşturulan iş parçacığına veya NULL'e hatası döndürür. Çağrı [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) genişletilmiş hata bilgilerini almak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) bu işlev parametreleri hakkında daha fazla bilgi için.  
  
 Bu işlev çağrıları `CreateThread` iş parçacığı oluşturmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
