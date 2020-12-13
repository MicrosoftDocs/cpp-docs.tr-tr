---
description: 'Daha fazla bilgi edinin: CSingleLock sınıfı'
title: CSingleLock sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 7fa4fe32ce38bf47ede1b6ac133d1a057907f9c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342862"
---
# <a name="csinglelock-class"></a>CSingleLock sınıfı

Çok iş parçacıklı programda bir kaynağa erişimi denetlemek için kullanılan erişim denetimi mekanizmasını temsil eder.

## <a name="syntax"></a>Syntax

```
class CSingleLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSingleLock:: CSingleLock](#csinglelock)|Bir `CSingleLock` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSingleLock:: ıskilitlendi](#islocked)|Nesnenin kilitlenip kilitlenmediğini belirler.|
|[CSingleLock:: Lock](#lock)|Bir eşitleme nesnesi bekler.|
|[CSingleLock:: unlock](#unlock)|Bir eşitleme nesnesi yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CSingleLock` taban sınıfına sahip değildir.

[Csemafor](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [Ccriticalhandle bölümü](../../mfc/reference/ccriticalsection-class.md)ve [CEvent](../../mfc/reference/cevent-class.md)eşitleme sınıflarını kullanmak için, bir veya CMultiLock nesnesi oluşturmanız gerekir, bu da `CSingleLock` eşitleme nesnesini beklemek ve serbest bırakmak için kullanın. [](../../mfc/reference/cmultilock-class.md) `CSingleLock`Tek seferde yalnızca bir nesne beklemeniz gerektiğinde kullanın. `CMultiLock`Belirli bir zamanda kullanabileceğiniz birden çok nesne olduğunda kullanın.

Bir nesnesi kullanmak için `CSingleLock` , oluşturucusunu denetlenen kaynağın sınıfında bir üye işlevi içinde çağırın. Ardından, kaynağın kullanılabilir olup olmadığını anlamak için [ıskilitli](#islocked) üye işlevini çağırın. Varsa, üye işlevinin geri kalanı ile devam edin. Kaynak kullanılamıyorsa, kaynağın serbest bırakılması için belirli bir süre bekleyin ya da hata döndürür. Kaynak kullanıldıktan sonra, [](#unlock) `CSingleLock` nesne yeniden kullanılacaksa ya da `CSingleLock` nesnenin yok edilmesi için unlock işlevini çağırın.

`CSingleLock` nesneler, [CSyncObject](../../mfc/reference/csyncobject-class.md)'ten türetilmiş bir nesne varlığını gerektirir. Bu genellikle denetlenen kaynağın sınıfının bir veri üyesidir. Nesneleri kullanma hakkında daha fazla bilgi için `CSingleLock` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSingleLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a> CSingleLock:: CSingleLock

Bir `CSingleLock` nesnesi oluşturur.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*Nesnesini*<br/>
Erişilecek eşitleme nesnesine işaret eder. NULL olamaz.

*bInitialLock*<br/>
Başlangıçta sağlanan nesneye erişmeyi denemeyeceğinizi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle denetlenen kaynağın bir erişim üye işlevinin içinden çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a> CSingleLock:: ıskilitlendi

Nesneyle ilişkilendirilen nesnenin `CSingleLock` sinyalsiz (kullanılamaz) olup olmadığını belirler.

```
BOOL IsLocked();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne kilitliyse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a> CSingleLock:: Lock

Oluşturucuya sağlanan eşitleme nesnesi tarafından denetlenen kaynağa erişim kazanmak için bu işlevi çağırın `CSingleLock` .

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesinin kullanılabilir (sinyal) için bekleyeceği süreyi belirtir. SONSUZ ise, `Lock` nesne döndürülmeden önce sinyallendirilene kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesine işaret edildiyse, `Lock` başarıyla döndürülür ve iş parçacığı artık nesnenin sahibi olur. Eşitleme nesnesi sinyalsiz (kullanılamaz) ise, `Lock` eşitleme nesnesinin *dwTimeOut* parametresinde belirtilen milisaniye sayısına kadar sinyal vermesini bekler. Eşitleme nesnesi belirtilen süre içinde sinyal getirmediyseniz, `Lock` hata döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a> CSingleLock:: unlock

Tarafından sahip olunan eşitleme nesnesini yayınlar `CSingleLock` .

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Serbest bırakma erişimi sayısı. 0 ' dan büyük olmalıdır. Belirtilen miktar nesnenin sayımının en büyük değerini aşmasına neden olacaksa, sayı değiştirilmez ve işlev FALSE değerini döndürür.

*lPrevCount*<br/>
Eşitleme nesnesinin önceki sayısını alacak bir değişkene işaret eder. NULL ise, önceki sayı döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev `CSingleLock` yok edicisi tarafından çağırılır.

Bir semaforun birden fazla erişim sayısını serbest bırakmanız gerekiyorsa, ikinci biçimini kullanın `Unlock` ve serbest bırakma erişimi sayısını belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock sınıfı](../../mfc/reference/cmultilock-class.md)
