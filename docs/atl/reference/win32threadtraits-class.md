---
title: "Win32ThreadTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf4fd3ffaf2fc4a035fdecf679ab507ebb557f38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits sınıfı
Bu sınıf için bir Windows iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanmayacaksa kullanın.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Statik) CRT işlevleri kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı özellikleri belirli bir iş parçacığı türü için bir oluşturma işlevi sağlayan sınıflarıdır. Oluşturma işlevi Windows aynı imza ve semantiklerine sahip [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi.  
  
 İş parçacığı özellikleri aşağıdaki sınıflar tarafından kullanılır:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 İş parçacığı CRT işlevleri kullanacaksanız kullanmak [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="createthread"></a>Win32ThreadTraits::CreateThread  
 CRT işlevleri kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevini çağırın.  
  
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
  
 Bu işlev çağrılarını `CreateThread` iş parçacığı oluşturulamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
