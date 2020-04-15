---
title: CSyncObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: ebfbc185cdca2effc96ce2e6d96d05f997c52bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365980"
---
# <a name="csyncobject-class"></a>CSyncObject Sınıfı

Win32'deki eşitleme nesnelerinde ortak işlevsellik sağlayan saf sanal sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CSyncObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Bir `CSyncObject` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSyncObject::Kilit](#lock)|Eşitleme nesnesine erişim kazanır.|
|[CSyncObject::Kilidini Aç](#unlock)|Eşitleme nesnesine erişim kazanır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSyncObject::operatör KOLU](#operator_handle)|Eşitleme nesnesine erişim sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|Altta yatan eşitleme nesnesinin tutamacı.|

## <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıf Kitaplığı, `CSyncObject`'den türetilen birkaç sınıf sağlar. Bunlar [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), ve [CSemaphore](../../mfc/reference/csemaphore-class.md)vardır.

Eşitleme nesnelerinin nasıl kullanılacağı hakkında bilgi için [Multithreading: Synchronization Classes nasıl kullanılır makalesine](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a>CSyncObject::CSyncObject

Verilen adla bir eşitleme nesnesi oluşturuyor.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Nesnenin adı. NULL ise, *pstrName* null olacaktır.

## <a name="csyncobjectlock"></a><a name="lock"></a>CSyncObject::Kilit

Eşitleme nesnesi tarafından denetlenen kaynağa erişmek için bu işlevi çağırın.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Eşitleme nesnesinin kullanılabilir olmasını beklemek için milisaniye cinsinden süreyi belirtir (sinyal). SONSUZ ise, `Lock` geri dönmeden önce nesne sinyal verilene kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesi sinyal vereli, `Lock` başarıyla döndürecek ve iş parçacığı artık nesneye sahip. Eşitleme nesnesi sinyal yoksa (kullanılamıyorsa), `Lock` eşitleme nesnesinin *dwTimeOut* parametresinde belirtilen milisaniye sayısına kadar sinyal olmasını bekler. Eşitleme nesnesi belirtilen süre içinde sinyal edilemediyse, `Lock` hata döndürür.

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a>CSyncObject::m_hObject

Altta yatan eşitleme nesnesinin tutamacı.

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a>CSyncObject::operatör KOLU

`CSyncObject` Nesnenin tutamacını almak için bu işleci kullanın.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, eşitleme nesnesinin tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Windows API'lerini doğrudan aramak için tutamacı kullanabilirsiniz.

## <a name="csyncobjectunlock"></a><a name="unlock"></a>CSyncObject::Kilidini Aç

Parametreleri `Unlock` olmayan bildirim saf bir sanal işlevdir ve 'den `CSyncObject`kaynaklanan tüm sınıflar tarafından geçersiz kılınması gerekir.

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lSay*<br/>
Varsayılan uygulama tarafından kullanılmaz.

*lpPrevCount*<br/>
Varsayılan uygulama tarafından kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

İki parametreile bildirimin varsayılan uygulaması her zaman TRUE döndürür. Bu işlev, çağrı iş parçacığının sahip olduğu eşitleme nesnesine erişimi serbest bırakmak için çağrılır. İkinci bildirim, denetlenen bir kaynağın birden fazla erişimine izin veren semaforlar gibi eşitleme nesneleri için sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
