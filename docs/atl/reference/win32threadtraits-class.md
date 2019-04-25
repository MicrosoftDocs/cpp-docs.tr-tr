---
title: Win32ThreadTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: da4b8b3d5a41ab16dc2027fd632c56158afd3b97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275944"
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

İş parçacığı nitelikler iş parçacığı belirli bir tür için bir oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi aynı imza ve semantiğine sahip Windows [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) işlevi.

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

*lpsa*<br/>
Yeni iş parçacığı için güvenlik öznitelikleri.

*dwStackSize*<br/>
Yeni iş parçacığı için yığın boyutu.

*pfnThreadProc*<br/>
Yeni iş parçacığının iş parçacığı yordamı.

*pvParam*<br/>
İş parçacığı yordama iletilecek parametre.

*dwCreationFlags*<br/>
Oluşturma (0 veya CREATE_SUSPENDED) işaretler.

*pdwThreadId*<br/>
[out] Başarı durumunda, yeni oluşturulan iş parçacığının iş parçacığı kimliği alır, DWORD değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı, yeni oluşturulan iş parçacığına veya NULL'e hatası döndürür. Çağrı [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) genişletilmiş hata bilgilerini almak için.

### <a name="remarks"></a>Açıklamalar

Bkz: [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) bu işlev parametreleri hakkında daha fazla bilgi için.

Bu işlev çağrıları `CreateThread` iş parçacığı oluşturmak için.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
