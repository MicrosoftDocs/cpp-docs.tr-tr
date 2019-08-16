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
ms.openlocfilehash: d086a42f5dcdf005d10c8853776da66b691a8e11
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495468"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits sınıfı

Bu sınıf, bir Windows iş parçacığı için oluşturma işlevi sağlar. İş parçacığı CRT işlevlerini kullanmayacak şekilde bu sınıfı kullanın.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class Win32ThreadTraits
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Win32ThreadTraits:: CreateThread](#createthread)|Se CRT işlevlerini kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı nitelikleri, belirli bir iş parçacığı türü için oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi, Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işleviyle aynı imzaya ve semantiğe sahiptir.

İş parçacığı nitelikleri aşağıdaki sınıflar tarafından kullanılır:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

İş parçacığı CRT işlevleri kullanıyorsa, bunun yerine [Crtthreadnitelikler](../../atl/reference/crtthreadtraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="createthread"></a>Win32ThreadTraits:: CreateThread

CRT işlevlerini kullanmamalıdır bir iş parçacığı oluşturmak için bu işlevi çağırın.

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
Yeni iş parçacığının güvenlik öznitelikleri.

*dwStackSize*<br/>
Yeni iş parçacığının yığın boyutu.

*pfnThreadProc*<br/>
Yeni iş parçacığının iş parçacığı yordamı.

*pvParam*<br/>
İş parçacığı yordamına geçirilecek parametre.

*dwCreationFlags*<br/>
Oluşturma bayrakları (0 veya CREATE_SUSPENDED).

*Pdwthreadıd*<br/>
dışı Başarılı olan DWORD değişkeninin adresi, yeni oluşturulan iş parçacığının iş parçacığı KIMLIĞINI alır.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iş parçacığına olan tanıtıcıyı veya hatada NULL değerini döndürür. Genişletilmiş hata bilgilerini almak için [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 'yi çağırın.

### <a name="remarks"></a>Açıklamalar

Bu işleve yönelik parametreler hakkında daha fazla bilgi için bkz. [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) .

Bu işlev, `CreateThread` iş parçacığını oluşturmak için çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
