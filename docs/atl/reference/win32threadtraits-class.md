---
title: Win32ThreadTraits Sınıfı
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
ms.openlocfilehash: 64f02293508894a70f36c29d5032c9ba8f250c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325796"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits Sınıfı

Bu sınıf, bir Windows iş parçacığı için oluşturma işlevini sağlar. Iş parçacığı CRT işlevlerini kullanmıyorsa bu sınıfı kullanın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class Win32ThreadTraits
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Win32ThreadTraits::CreateThread](#createthread)|(Statik) CRT işlevlerini kullanmaması gereken bir iş parçacığı oluşturmak için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı özellikleri, belirli bir iş parçacığı türü için oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi, Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işleviyle aynı imzaya ve anlambilime sahiptir.

İş parçacığı özellikleri aşağıdaki sınıflar tarafından kullanılır:

- [Cthreadpool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

İş parçacığı CRT işlevlerini kullanacaksa, bunun yerine [CRTThreadTraits'ı](../../atl/reference/crtthreadtraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="win32threadtraitscreatethread"></a><a name="createthread"></a>Win32ThreadTraits::CreateThread

CRT işlevlerini kullanmaması gereken bir iş parçacığı oluşturmak için bu işlevi çağırın.

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
İş parçacığı yordamına geçirilecek parametre.

*dwCreationFlags*<br/>
Oluşturma bayrakları (0 veya CREATE_SUSPENDED).

*pdwThreadId*<br/>
[çıkış] DWORD değişkeninin adresi, başarı, yeni oluşturulan iş parçacığının iş parçacığı kimliğini alır.

### <a name="return-value"></a>Dönüş Değeri

Hata da yeni oluşturulan iş parçacığı veya NULL için tanıtıcı döndürür. Genişletilmiş hata bilgilerini almak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) arayın.

### <a name="remarks"></a>Açıklamalar

Bu işlevin parametreleri hakkında daha fazla bilgi için [CreateThread'e](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) bakın.

Bu işlev `CreateThread` iş parçacığı oluşturmak için çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
