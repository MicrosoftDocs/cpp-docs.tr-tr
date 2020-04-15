---
title: CSingleLock Sınıfı
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
ms.openlocfilehash: 231397228d94e58665602453b5d377571e24a967
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318266"
---
# <a name="csinglelock-class"></a>CSingleLock Sınıfı

Çok iş parçacığı yla bir programdaki kaynağa erişimi denetlemede kullanılan erişim denetim mekanizmasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CSingleLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Bir `CSingleLock` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSingleLock::Kilitli](#islocked)|Nesnenin kilitli olup olmadığını belirler.|
|[CSingleLock::Kilit](#lock)|Eşitleme nesnesi üzerinde bekler.|
|[CSingleLock::Kilidini Aç](#unlock)|Eşitleme nesnesi serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

`CSingleLock`taban sınıfa sahip değildir.

[CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)ve [CEvent](../../mfc/reference/cevent-class.md)eşitleme sınıflarını kullanmak için, eşitleme nesnesini beklemek ve serbest bırakmak için bir `CSingleLock` veya [CMultiLock](../../mfc/reference/cmultilock-class.md) nesnesi oluşturmanız gerekir. Aynı `CSingleLock` anda yalnızca bir nesne üzerinde beklemeniz gerektiğinde kullanın. Belirli `CMultiLock` bir anda kullanabileceğiniz birden çok nesne olduğunda kullanın.

Bir `CSingleLock` nesneyi kullanmak için, yapı oluşturucuyu denetitilen kaynağın sınıfındaki bir üye işlevin içinde çağırın. Ardından, kaynağın kullanılabilir olup olmadığını belirlemek için [Kilitli](#islocked) üye işlevini arayın. Eğer varsa, üye işlevin geri kalanı ile devam edin. Kaynak kullanılamıyorsa, kaynağın serbest bırakılması için belirli bir süre bekleyin veya başarısızlığı döndürün. Kaynağın kullanımı tamamlandıktan sonra, [Unlock](#unlock) `CSingleLock` nesne yeniden kullanılacaksa Kilidi Aç işlevini `CSingleLock` çağırın veya nesnenin yok edilmesine izin verin.

`CSingleLock`nesneler [CSyncObject](../../mfc/reference/csyncobject-class.md)türetilen bir nesnenin varlığını gerektirir. Bu genellikle denetitilen kaynağın sınıfının bir veri üyesidir. Nesnelerin nasıl kullanılacağı `CSingleLock` hakkında daha fazla bilgi için [Multithreading: Synchronization Classes nasıl kullanılır makalesine](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSingleLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a>CSingleLock::CSingleLock

Bir `CSingleLock` nesne inşa eder.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pobject*<br/>
Erişilecek eşitleme nesnesine işaret edilir. NULL olamaz.

*bInitialLock*<br/>
Başlangıçta sağlanan nesneye erişmeye çalışıp çalışmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle denetitilen kaynağın bir erişim üyesi işlevi içinden çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a>CSingleLock::Kilitli

Nesneyle ilişkili nesnenin `CSingleLock` sinyal yoksa (kullanılanınmaz) olup olmadığını belirler.

```
BOOL IsLocked();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne kilitliyse sıfırsız; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a>CSingleLock::Kilit

`CSingleLock` Oluşturucuya sağlanan eşitleme nesnesi tarafından denetlenen kaynağa erişmek için bu işlevi çağırın.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesinin kullanılabilir olmasını bekleme süresini belirtir (sinyal). SONSUZ ise, `Lock` geri dönmeden önce nesne sinyal verilene kadar bekler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Eşitleme nesnesi sinyal vereli, `Lock` başarıyla döndürecek ve iş parçacığı artık nesneye sahip. Eşitleme nesnesi sinyal yoksa (kullanılamıyorsa), `Lock` eşitleme nesnesinin *dwTimeOut* parametresinde belirtilen milisaniye sayısına kadar sinyal olmasını bekler. Eşitleme nesnesi belirtilen süre içinde sinyal edilemediyse, `Lock` hata döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a>CSingleLock::Kilidini Aç

`CSingleLock`Sahip olduğu eşitleme nesnesini serbest bırakır.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lSay*<br/>
Serbest bırakılamayacak erişim sayısı. 0'dan büyük olmalı. Belirtilen tutar nesnenin sayısının en büyük sayısını aşması durumunda, sayım değiştirilmez ve işlev FALSE döndürür.

*lPrevCount*<br/>
Eşitleme nesnesinin önceki sayısını almak için bir değişkene işaret edin. NULL ise, önceki sayım döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu fonksiyon 'yıkıcı tarafından `CSingleLock`adlandırılır.

Bir semaforun birden fazla erişim sayısını serbest bırakmanız gerekiyorsa, `Unlock` ikinci formu kullanın ve yayımlanacak erişim sayısını belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock Sınıfı](../../mfc/reference/cmultilock-class.md)
