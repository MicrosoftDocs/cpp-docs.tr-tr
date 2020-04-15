---
title: CRTThreadTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: a7cfddc64e8c1b4e192e718d05812e385fbe08ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331028"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits Sınıfı

Bu sınıf bir CRT iş parçacığı için oluşturma işlevini sağlar. Iş parçacığı CRT işlevlerini kullanacaksa bu sınıfı kullanın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CRTThreadTraits
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRTThreadÖzellikleri::CreateThread](#createthread)|(Statik) CRT işlevlerini kullanabilen bir iş parçacığı oluşturmak için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı özellikleri, belirli bir iş parçacığı türü için oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi, Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işleviyle aynı imzaya ve anlambilime sahiptir.

İş parçacığı özellikleri aşağıdaki sınıflar tarafından kullanılır:

- [Cthreadpool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

İş parçacığı CRT işlevlerini kullanmıyorsa, bunun yerine [Win32ThreadTraits'ı](../../atl/reference/win32threadtraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="crtthreadtraitscreatethread"></a><a name="createthread"></a>CRTThreadÖzellikleri::CreateThread

CRT işlevlerini kullanabilen bir iş parçacığı oluşturmak için bu işlevi çağırın.

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

Bu işlev iş parçacığı oluşturmak için [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
