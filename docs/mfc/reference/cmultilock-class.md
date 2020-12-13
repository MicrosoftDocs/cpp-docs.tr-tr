---
description: 'Daha fazla bilgi edinin: CMultiLock sınıfı'
title: CMultiLock sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
ms.openlocfilehash: 1a45c3c302b9f8028061649e2a0d270d47ed58aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331541"
---
# <a name="cmultilock-class"></a>CMultiLock sınıfı

Çok iş parçacıklı bir programdaki kaynaklara erişimi denetlemek için kullanılan erişim denetimi mekanizmasını temsil eder.

## <a name="syntax"></a>Syntax

```
class CMultiLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiLock:: CMultiLock](#cmultilock)|Bir `CMultiLock` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMultiLock:: ıskilitlendi](#islocked)|Dizideki belirli bir eşitleme nesnesinin kilitlenip kilitlenmediğini belirler.|
|[CMultiLock:: Lock](#lock)|Eşitleme nesnelerinin dizisini bekler.|
|[CMultiLock:: unlock](#unlock)|Sahip olunan tüm eşitleme nesnelerini yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CMultiLock` taban sınıfına sahip değildir.

[Csemafor](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md)ve [CEvent](../../mfc/reference/cevent-class.md)eşitleme sınıflarını kullanmak Için, bir `CMultiLock` veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturarak eşitleme nesnesini bekleyip serbest bırakabilirsiniz. `CMultiLock`Belirli bir zamanda kullanabileceğiniz birden çok nesne olduğunda kullanın. `CSingleLock`Tek seferde yalnızca bir nesne beklemeniz gerektiğinde kullanın.

Bir nesnesi kullanmak için `CMultiLock` önce beklemek istediğiniz eşitleme nesnelerinin bir dizisini oluşturun. Sonra, `CMultiLock` denetlenen kaynağın sınıfında bir üye işlevi içinde nesnenin oluşturucusunu çağırın. Ardından, bir kaynağın kullanılabilir olup olmadığını (sinyal) öğrenmek için [kilit](#lock) üye işlevini çağırın. Biri ise, üye işlevinin geri kalanı ile devam edin. Kullanılabilir kaynak yoksa, bir kaynağın serbest bırakılması için belirli bir süre bekleyin ya da hata döndürür. Bir kaynak kullanıldıktan sonra, [](#unlock) `CMultiLock` nesne yeniden kullanılacaksa ya da `CMultiLock` nesnenin yok edilmesi için unlock işlevini çağırın.

`CMultiLock` bir iş parçacığında yanıt verebildiği çok sayıda nesne olduğunda nesneler en çok yararlıdır `CEvent` . Tüm işaretçileri içeren bir dizi oluşturun `CEvent` ve çağırın `Lock` . Bu, iş parçacığının bir olaydan birine sinyal alınana kadar beklemesini sağlar.

Nesneleri kullanma hakkında daha fazla bilgi için `CMultiLock` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMultiLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="cmultilockcmultilock"></a><a name="cmultilock"></a> CMultiLock:: CMultiLock

Bir `CMultiLock` nesnesi oluşturur.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*ppObjects*<br/>
Beklenen eşitleme nesnelerine yönelik işaretçiler dizisi. NULL olamaz.

*dwCount*<br/>
*PpObjects* içindeki nesne sayısı. 0 ' dan büyük olmalıdır.

*bInitialLock*<br/>
Başlangıçta sağlanan nesnelerden birine erişmeyi denemeyeceğinizi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bekleme için eşitleme nesneleri dizisi oluşturulduktan sonra çağrılır. Genellikle eşitleme nesnelerinden birinin kullanılabilir hale gelmesini beklemek zorunda olan iş parçacığı içinden çağrılır.

## <a name="cmultilockislocked"></a><a name="islocked"></a> CMultiLock:: ıskilitlendi

Belirtilen nesnenin sinyalsiz (kullanılamaz) olup olmadığını belirler.

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>Parametreler

*dwItem*<br/>
Durumu sorgulanmakta olan nesneye karşılık gelen nesneler dizisindeki dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen nesne kilitliyse sıfır dışı; Aksi takdirde 0.

## <a name="cmultilocklock"></a><a name="lock"></a> CMultiLock:: Lock

Oluşturucuya sağlanan eşitleme nesneleriyle denetlenen bir veya daha fazla kaynağa erişim kazanmak için bu işlevi çağırın `CMultiLock` .

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesinin kullanılabilir (sinyal) için bekleyeceği süreyi belirtir. SONSUZ ise, `Lock` nesne döndürülmeden önce sinyallendirilene kadar bekler.

*bWaitForAll*<br/>
Tüm nesnelerin, döndürmeden önce aynı anda döndürülüp döndürülmeyeceğini belirtir. FALSE ise, `Lock` nesnelerden herhangi biri beklediğinde döndürülecek olur.

*dwWakeMask*<br/>
Beklemeyi durdurmaya izin verilen diğer koşulları belirtir. Bu parametre için kullanılabilir seçeneklerin tam listesi için, Windows SDK [MsgWaitForMultipleObjects](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects) öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

`Lock`Başarısız olursa,-1 döndürür. Başarılı olursa, aşağıdaki değerlerden birini döndürür:

- WAIT_OBJECT_0 ve WAIT_OBJECT_0 + (nesne sayısı-1) arasında

   *BWaitForAll* değeri true ise tüm nesneler (kullanılabilir) olarak gösterilir. *BWaitForAll* yanlış ise, dönüş değeri-WAIT_OBJECT_0, sinyal edilen (kullanılabilir) nesnenin nesneleri dizisindeki dizindir.

- WAIT_OBJECT_0 + (nesne sayısı)

   *DwWakeMask* içinde belirtilen bir olay, iş parçacığının giriş kuyruğunda kullanılabilir.

- WAIT_ABANDONED_0 ve WAIT_ABANDONED_0 + (nesne sayısı-1) arasında

   *BWaitForAll* değeri true ise, tüm nesneler sinyal alınır ve en az bir tane bir adet nesne, bırakılan mutex nesnesidir. *BWaitForAll* yanlış ise, dönüş değeri-WAIT_ABANDONED_0, bırakılan mutex nesnesinin nesne dizisindeki, beklemeyi karşılayan dizindir.

- WAIT_TIMEOUT

   *DwTimeOut* 'da belirtilen zaman aşımı aralığı, başarılı olmadan süre sonu ile doldu.

### <a name="remarks"></a>Açıklamalar

*BWaitForAll* değeri true ise, `Lock` tüm eşitleme nesneleri aynı anda sinyalleşecek şekilde, başarıyla geri döndürülür. *BWaitForAll* yanlış ise, `Lock` bir veya daha fazla eşitleme nesnesi sinyalden sonra geri döndürülür.

`Lock`Hemen geri dönemeyebilirsiniz, döndürmeden önce *dwTimeOut* parametresinde belirtilen milisaniyeye daha fazla süre bekleyemez. *DwTimeOut* sonsuz ise, `Lock` bir nesneye erişim elde edilene veya *dwWakeMask* içinde belirtilen bir koşul karşılanana kadar döndürülmeyecektir. Aksi takdirde, `Lock` bir eşitleme nesnesi elde edebilse, başarıyla döndürülür; değilse, hata döndürür.

## <a name="cmultilockunlock"></a><a name="unlock"></a> CMultiLock:: unlock

Tarafından sahip olunan eşitleme nesnesini yayınlar `CMultiLock` .

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Serbest bırakma için başvuru sayısı. 0 ' dan büyük olmalıdır. Belirtilen miktar nesnenin sayımının en büyük değerini aşmasına neden olacaksa, sayı değiştirilmez ve işlev FALSE değerini döndürür.

*lPrevCount*<br/>
Eşitleme nesnesi için önceki sayıyı almak üzere bir değişkene işaret eder. NULL ise, önceki sayı döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev `CMultiLock` yok edicisi tarafından çağırılır.

İlk biçimi `Unlock` tarafından yönetilen eşitleme nesnesinin kilidini açmaya çalışır `CMultiLock` . İkinci biçimi `Unlock` `CSemaphore` tarafından sahip olunan nesnelerin kilidini açmaya çalışır `CMultiLock` . `CMultiLock`Herhangi bir kilitli `CSemaphore` nesne içermiyorsa, işlev FALSE döndürür; aksi takdırde, true döndürür. *lCount* ve *lpPrevCount* , [CSingleLock:: unlock](../../mfc/reference/csinglelock-class.md#unlock)parametreleriyle tamamen aynıdır. İkinci biçimi `Unlock` çok kilitleme durumları için nadiren geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
