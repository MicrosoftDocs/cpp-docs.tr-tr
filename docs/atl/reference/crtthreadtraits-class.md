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
ms.openlocfilehash: c182840ed3592a229b8d6c7b98930ade57a18b25
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883027"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits sınıfı
Bu sınıf için CRT iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanacaksanız kullanın.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(Statik) CRT işlevlerinin kullanabileceğiniz iş parçacığı oluşturmak için bu işlevi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı nitelikler iş parçacığı belirli bir tür için bir oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi aynı imza ve semantiğine sahip Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi.  
  
 İş parçacığı nitelikler aşağıdaki sınıflar tarafından kullanılır:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 İş parçacığı CRT işlevleri kullanmayan kullanırsanız [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="createthread"></a>  CRTThreadTraits::CreateThread  
 CRT işlevlerinin kullanabileceğiniz iş parçacığı oluşturmak için bu işlevi çağırın.  
  
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
  
 Bu işlev çağrıları [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) iş parçacığı oluşturmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
