---
description: 'Daha fazla bilgi edinin: CSyncObject sınıfı'
title: CSyncObject sınıfı
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
ms.openlocfilehash: 5743f632f9a8c482ac15995e8d2429851ba015d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318604"
---
# <a name="csyncobject-class"></a>CSyncObject sınıfı

Win32 içindeki eşitleme nesnelerinde ortak işlevselliği sağlayan saf bir sanal sınıf.

## <a name="syntax"></a>Syntax

```
class CSyncObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject:: CSyncObject](#csyncobject)|Bir `CSyncObject` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject:: Lock](#lock)|Eşitleme nesnesine erişim kazanır.|
|[CSyncObject:: unlock](#unlock)|Eşitleme nesnesine erişim kazanır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject:: operator işleci](#operator_handle)|Eşitleme nesnesine erişim sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject:: m_hObject](#m_hobject)|Temel eşitleme nesnesinin tanıtıcısı.|

## <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı, öğesinden türetilmiş çeşitli sınıflar sağlar `CSyncObject` . Bunlar [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [Ccriticalhandle bölümü](../../mfc/reference/ccriticalsection-class.md)ve [csemafor](../../mfc/reference/csemaphore-class.md)' dir.

Eşitleme nesnelerini kullanma hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a> CSyncObject:: CSyncObject

Sağlanan ada sahip bir eşitleme nesnesi oluşturur.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Nesnenin adı. NULL ise *pstrName* null olur.

## <a name="csyncobjectlock"></a><a name="lock"></a> CSyncObject:: Lock

Eşitleme nesnesi tarafından denetlenen kaynağa erişim kazanmak için bu işlevi çağırın.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Eşitleme nesnesinin kullanılabilir olması için beklenecek süreyi milisaniye olarak belirtir (sinyal). SONSUZ ise, `Lock` nesne döndürülmeden önce sinyallendirilene kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesine işaret edildiyse, `Lock` başarıyla döndürülür ve iş parçacığı artık nesnenin sahibi olur. Eşitleme nesnesi sinyalsiz (kullanılamaz) ise, `Lock` eşitleme nesnesinin *dwTimeOut* parametresinde belirtilen milisaniye sayısına kadar sinyal vermesini bekler. Eşitleme nesnesi belirtilen süre içinde sinyal getirmediyseniz, `Lock` hata döndürür.

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a> CSyncObject:: m_hObject

Temel eşitleme nesnesinin tanıtıcısı.

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a> CSyncObject:: operator işleci

Nesnenin tanıtıcısını almak için bu işleci kullanın `CSyncObject` .

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, eşitleme nesnesinin tanıtıcısı; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

İşleyiciyi doğrudan Windows API 'Leri çağırmak için kullanabilirsiniz.

## <a name="csyncobjectunlock"></a><a name="unlock"></a> CSyncObject:: unlock

`Unlock`Parametresi olmayan bildirimi, saf bir sanal işlevdir ve öğesinden türetilen tüm sınıflar tarafından geçersiz kılınmalıdır `CSyncObject` .

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Varsayılan uygulama tarafından kullanılmaz.

*lpPrevCount*<br/>
Varsayılan uygulama tarafından kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İki parametreli bildirimin varsayılan uygulama her zaman TRUE değerini döndürür. Bu işlev, çağıran iş parçacığının sahip olduğu eşitleme nesnesine erişimi serbest bırakmak için çağrılır. İkinci bildirim, denetimli bir kaynağa birden fazla erişime izin veren Semaforlar gibi eşitleme nesneleri için sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
