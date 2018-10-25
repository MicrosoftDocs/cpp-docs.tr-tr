---
title: CSingleLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 063ad23a9d356af0cac6c5b9dd8903e81530d2df
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061345"
---
# <a name="csinglelock-class"></a>CSingleLock sınıfı

Çoklu iş parçacığı kullanan programda bir kaynağa erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CSingleLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Oluşturur bir `CSingleLock` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSingleLock::IsLocked](#islocked)|Nesne kilitli olduğunu belirler.|
|[CSingleLock::Lock](#lock)|Bir eşitleme nesnesi üzerinde bekler.|
|[CSingleLock::Unlock](#unlock)|Bir eşitleme nesnesi serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

`CSingleLock` bir temel sınıfa sahip değil.

Eşitleme sınıfları kullanmak için [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), ve [CEvent](../../mfc/reference/cevent-class.md), ya da oluşturmalısınız bir `CSingleLock` veya [CMultiLock](../../mfc/reference/cmultilock-class.md) eşitleme nesneyi serbest nesnesini bekleyebilir. Kullanım `CSingleLock` yalnızca gerektiğinde bir kerede bir nesne üzerinde bekleyin. Kullanma `CMultiLock` kullanabileceğinizi belirli bir zamanda birden fazla nesne olduğunda.

Kullanılacak bir `CSingleLock` nesne, denetimli kaynak sınıfının oluşturucusuna bir üye işlevin içindeki çağırın. Ardından çağırın [IsLocked](#islocked) kaynak kullanılabilir olup olmadığını belirlemek için üye işlevi. İse, üye işlevi geri kalanı ile devam edin. Kaynak kullanılamıyorsa, zaman yayımlanacak kaynak için belirli bir süre bekleyin veya hata döndürür. Kaynak kullanımını tamamlandıktan sonra ya da çağrı [kilidini](#unlock) işlevinin `CSingleLock` nesnedir izin ver veya yeniden kullanılmak üzere `CSingleLock` nesne yok.

`CSingleLock` nesneleri gerektiren türetilmiş bir nesnenin durum [CSyncObject](../../mfc/reference/csyncobject-class.md). Denetimli kaynak sınıfının veri üyesi genellikle budur. Nasıl kullanılacağı hakkında daha fazla bilgi için `CSingleLock` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSingleLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="csinglelock"></a>  CSingleLock::CSingleLock

Oluşturur bir `CSingleLock` nesne.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*pObject*<br/>
Erişilecek eşitleme nesnesi işaret eder. NULL olamaz.

*bInitialLock*<br/>
Başlangıçta sağlanan nesneye erişme girişimi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle denetimli kaynak içinde bir erişim üye işlevi çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

##  <a name="islocked"></a>  CSingleLock::IsLocked

Nesne ile ilişkili değilse belirler `CSingleLock` nesnedir nonsignaled (kullanılamıyor).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin kilitli olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

##  <a name="lock"></a>  CSingleLock::Lock

Sağlanan eşitleme nesnesi tarafından denetlenen bir kaynağa erişmek için bu işlevi çağırın `CSingleLock` Oluşturucusu.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesi kullanılabilir olması beklenecek süreyi belirtir (işareti). SONSUZ ise `Lock` döndürmeden önce nesne sinyal kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesi sinyal vermediyse, `Lock` başarıyla döndürür ve iş parçacığı nesneye artık sahip. Eşitleme nesnesi nonsignaled ise (kullanılamıyor) `Lock` belirtilen milisaniye sayısı kadar sinyal haline eşitleme nesnesi için bekleyeceği *dwTimeOut* parametresi. Eşitleme nesnesi belirtilen sürede, sinyal haline değil, `Lock` hatası döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

##  <a name="unlock"></a>  CSingleLock::Unlock

Eşitleme nesnesi tarafından sahip olunan serbest `CSingleLock`.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Serbest bırakmak için erişim sayısı. 0'dan büyük olmalıdır. Belirtilen nesnenin sayısı, en yüksek süreyi aşmasına yol açıyorsa sayısı değiştirilmez ve işlev false değerini döndürür.

*lPrevCount*<br/>
Önceki eşitleme nesnesi sayısını almak için bir değişkene işaret eder. NULL ise, önceki sayısı döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağıran `CSingleLock`'s yıkıcı.

Semafor birden fazla erişim sayısı serbest bırakmak gerekiyorsa ikinci biçimi kullanmak `Unlock` ve serbest bırakmak için erişimleri sayısını belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock Sınıfı](../../mfc/reference/cmultilock-class.md)
