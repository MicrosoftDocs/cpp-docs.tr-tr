---
title: CSyncObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91a3978b83be0cc1bc85d57cbde87d17eb4cc6d6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082808"
---
# <a name="csyncobject-class"></a>CSyncObject sınıfı

Win32'de eşitleme nesneleriyle ortak işlevselliği sağlayan saf sanal sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CSyncObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Oluşturur bir `CSyncObject` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject::Lock](#lock)|Erişim için eşitleme nesnesi.|
|[CSyncObject::Unlock](#unlock)|Erişim için eşitleme nesnesi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject::operator TANITICISI](#operator_handle)|Eşitleme nesnesi erişim sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|Temel alınan eşitleme nesnesi için tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı ile türetilmiş birkaç sınıflarını sağlar `CSyncObject`. Bunlar [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), ve [CSemaphore](../../mfc/reference/csemaphore-class.md).

Eşitleme nesneleri kullanma hakkında daha fazla bilgi için bkz [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="csyncobject"></a>  CSyncObject::CSyncObject

Belirtilen ada sahip bir eşitleme nesnesi oluşturur.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Nesne adı. NULL ise, *pstrName* null olacaktır.

##  <a name="lock"></a>  CSyncObject::Lock

Eşitleme nesnesi tarafından denetlenen bir kaynağa erişim elde etmek için bu işlevi çağırın.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
Eşitleme nesnesi kullanılabilir olması beklenecek milisaniye cinsinden süre miktarını belirtir. (işareti). SONSUZ ise `Lock` döndürmeden önce nesne sinyal kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesi sinyal vermediyse, `Lock` başarıyla döndürür ve iş parçacığı nesneye artık sahip. Eşitleme nesnesi nonsignaled ise (kullanılamıyor) `Lock` belirtilen milisaniye sayısı kadar sinyal haline eşitleme nesnesi için bekleyeceği *dwTimeOut* parametresi. Eşitleme nesnesi belirtilen sürede, sinyal haline değil, `Lock` hatası döndürür.

##  <a name="m_hobject"></a>  CSyncObject::m_hObject

Temel alınan eşitleme nesnesi için tanıtıcı.

```
HANDLE m_hObject;
```

##  <a name="operator_handle"></a>  CSyncObject::operator TANITICISI

Tanıtıcısını almak için bu işleci kullanın `CSyncObject` nesne.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, eşitleme nesnesi; tanıtıcısı Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı, doğrudan Windows API çağırmak için kullanabilirsiniz.

##  <a name="unlock"></a>  CSyncObject::Unlock

Bildirimi `Unlock` hiçbir parametre olmadan saf sanal işlevi olan ve türetilen tüm sınıflar tarafından geçersiz kılınmalıdır `CSyncObject`.

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

Varsayılan uygulama bildirimi iki parametre ile her zaman TRUE değerini döndürür. Bu işlev, çağıran iş parçacığına ait eşitleme nesnesi erişimi serbest bırakmak için çağrılır. Denetlenen bir kaynağın birden fazla erişim izni semaforlar gibi eşitleme nesneleri için ikinci bildirim sağlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

