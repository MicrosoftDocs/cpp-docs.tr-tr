---
title: Crtthreadnitelikler sınıfı
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
ms.openlocfilehash: 9e12e64041e38b8fa014815870132a75885014bf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496560"
---
# <a name="crtthreadtraits-class"></a>Crtthreadnitelikler sınıfı

Bu sınıf, bir CRT iş parçacığı için oluşturma işlevi sağlar. İş parçacığı CRT işlevlerini kullanacaksanız, bu sınıfı kullanın.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CRTThreadTraits
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Crtthreadnitelikler:: CreateThread](#createthread)|Se CRT işlevleri kullanılabilecek bir iş parçacığı oluşturmak için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı nitelikleri, belirli bir iş parçacığı türü için oluşturma işlevi sağlayan sınıflardır. Oluşturma işlevi, Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) işleviyle aynı imzaya ve semantiğe sahiptir.

İş parçacığı nitelikleri aşağıdaki sınıflar tarafından kullanılır:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

İş parçacığı CRT işlevlerini kullanmayacak, bunun yerine [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="createthread"></a>Crtthreadnitelikler:: CreateThread

CRT işlevleri kullanılabilecek bir iş parçacığı oluşturmak için bu işlevi çağırın.

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

Bu işlev, iş parçacığını oluşturmak için [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) öğesini çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
