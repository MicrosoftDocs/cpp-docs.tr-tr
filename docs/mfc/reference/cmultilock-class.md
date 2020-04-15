---
title: CMultiLock Sınıfı
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
ms.openlocfilehash: a051c6a510c53ac0c7c0a6efd8b4b5720080b264
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319708"
---
# <a name="cmultilock-class"></a>CMultiLock Sınıfı

Çok iş parçacığı yla yapılan bir programdaki kaynaklara erişimi denetlemede kullanılan erişim denetim mekanizmasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMultiLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMultiLock::CMultiLock](#cmultilock)|Bir `CMultiLock` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMultiLock::Kilitli](#islocked)|Dizideki belirli bir eşitleme nesnesinin kilitli olup olmadığını belirler.|
|[CMultiLock::Kilit](#lock)|Eşitleme nesneleri dizisinde bekler.|
|[CMultiLock::Kilidini Aç](#unlock)|Sahip olunan tüm eşitleme nesnelerini serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

`CMultiLock`taban sınıfa sahip değildir.

[CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md)ve [CEvent](../../mfc/reference/cevent-class.md)eşitleme sınıflarını kullanmak için, eşitleme nesnesini beklemek ve serbest bırakmak için bir `CMultiLock` veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturabilirsiniz. Belirli `CMultiLock` bir anda kullanabileceğiniz birden çok nesne olduğunda kullanın. Aynı `CSingleLock` anda yalnızca bir nesne üzerinde beklemeniz gerektiğinde kullanın.

Bir `CMultiLock` nesneyi kullanmak için, önce beklemek istediğiniz eşitleme nesnelerinden oluşan bir dizi oluşturun. Ardından, denetitilen kaynağın sınıfındaki bir üye işlevin içindeki nesnenin `CMultiLock` oluşturucusu çağırın. Ardından, kaynağın kullanılabilir olup olmadığını (sinyalli) belirlemek için [Kilit](#lock) üye işlevini arayın. Eğer varsa, üye işlevin geri kalanı ile devam edin. Kaynak yoksa, kaynağın serbest bırakılması için belirli bir süre bekleyin veya başarısızlığı döndürün. Kaynağın kullanımı tamamlandıktan sonra, [Unlock](#unlock) `CMultiLock` nesne yeniden kullanılacaksa Kilidi Aç işlevini `CMultiLock` çağırın veya nesnenin yok edilmesine izin verin.

`CMultiLock`nesneler, bir iş parçacığının yanıt verebileceği çok sayıda `CEvent` nesneye sahip olması yla en kullanışlı olan nesnelerdir. Tüm işaretçileri `CEvent` içeren bir dizi `Lock`oluşturun ve çağırın. Bu, olaylardan biri sinyal verilene kadar iş parçacığının beklemesine neden olur.

Nesnelerin nasıl kullanılacağı `CMultiLock` hakkında daha fazla bilgi için [Multithreading: Synchronization Classes nasıl kullanılır makalesine](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMultiLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="cmultilockcmultilock"></a><a name="cmultilock"></a>CMultiLock::CMultiLock

Bir `CMultiLock` nesne inşa eder.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*ppNesneler*<br/>
İzlenecek eşitleme nesnelerine işaretçiler dizisi. NULL olamaz.

*dwSay*<br/>
*ppObjects*nesnelerin sayısı. 0'dan büyük olmalı.

*bInitialLock*<br/>
Başlangıçta sağlanan nesnelerden herhangi biri erişmeye çalışıp çalışmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, üzerinde beklenilecek eşitleme nesneleri dizisini oluşturduktan sonra çağrılır. Genellikle eşitleme nesnelerinden birinin kullanılabilir olmasını beklemesi gereken iş parçacığı nın içinden çağrılır.

## <a name="cmultilockislocked"></a><a name="islocked"></a>CMultiLock::Kilitli

Belirtilen nesnenin sinyal yoksa (kullanılanınmaz) olup olmadığını belirler.

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>Parametreler

*dwÖğe*<br/>
Durumu sorgulanan nesneye karşılık gelen nesneler dizisindeki dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen nesne kilitliyse sıfırsız; aksi takdirde 0.

## <a name="cmultilocklock"></a><a name="lock"></a>CMultiLock::Kilit

`CMultiLock` Oluşturucuya sağlanan eşitleme nesneleri tarafından denetlenen kaynaklardan birine veya daha fazlasına erişmek için bu işlevi arayın.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesinin kullanılabilir olmasını bekleme süresini belirtir (sinyal). SONSUZ ise, `Lock` geri dönmeden önce nesne sinyal verilene kadar bekler.

*bWaitForAll*<br/>
Üzerinde bekleyen tüm nesnelerin döndürülmeden önce aynı anda sinyal verilip verilip verilip vermeyeceğini belirtir. FALSE ise, `Lock` üzerinde bekleyen nesnelerden herhangi biri sinyal verildiğinde geri döner.

*dwWakeMask*<br/>
Beklemeyi iptal etmesine izin verilen diğer koşulları belirtir. Bu parametre için kullanılabilir seçeneklerin tam listesi için Windows SDK'daki [MsgWaitForMultipleObjects](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarısız `Lock` olursa, döner - 1. Başarılı olursa, aşağıdaki değerlerden birini döndürür:

- WAIT_OBJECT_0 ile WAIT_OBJECT_0 + (nesne sayısı - 1) arasında

   *bWaitForAll* TRUE ise, tüm nesneler sinyal (kullanılabilir) işaretlenir. *bWaitForAll* FALSE ise, iade değeri - WAIT_OBJECT_0 sinyal (kullanılabilir) nesnenin nesnelerin dizideksi olduğunu.

- WAIT_OBJECT_0 + (nesne sayısı)

   *DwWakeMask'de* belirtilen bir olay iş parçacığının giriş kuyruğunda kullanılabilir.

- WAIT_ABANDONED_0 ve WAIT_ABANDONED_0 + (nesne sayısı - 1) arasında

   *bWaitForAll* TRUE ise, tüm nesneler sinyal ve nesnelerin en az biri terk edilmiş bir mutex nesnesidir. *bWaitForAll* FALSE ise, WAIT_ABANDONED_0 beklemeyi karşılayan terk edilmiş mutex nesnesinin nesne dizilimindeki dizindir.

- WAIT_TIMEOUT

   *dwTimeOut'ta* belirtilen zaman aşımı aralığı, bekleme nin başarılı olması olmadan sona erdi.

### <a name="remarks"></a>Açıklamalar

*bWaitForAll* TRUE ise, `Lock` tüm eşitleme nesneleri aynı anda sinyal olur olmaz başarıyla geri döner. *bWaitForAll* FALSE ise, `Lock` eşitleme nesnelerinden biri veya birkaçı sinyal verilir açılmaz geri döner.

`Lock` Hemen geri dönemezse, dönmeden önce *dwTimeOut* parametresinde belirtilen milisaniye sayısından daha fazla beklemez. *dwTimeOut* INFINITE ise, `Lock` bir nesneye erişim elde edilene veya *dwWakeMask'de* belirtilen bir koşul karşılanana kadar geri dönmez. Aksi takdirde, bir eşitleme nesnesi elde edebildiyseniz, `Lock` başarılı bir şekilde geri dönecektir; değilse, başarısızlığı döndürecektir.

## <a name="cmultilockunlock"></a><a name="unlock"></a>CMultiLock::Kilidini Aç

`CMultiLock`Sahip olduğu eşitleme nesnesini serbest bırakır.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lSay*<br/>
Yayımlanacak başvuru sayısı. 0'dan büyük olmalı. Belirtilen tutar nesnenin sayısının en büyük sayısını aşması durumunda, sayım değiştirilmez ve işlev FALSE döndürür.

*lPrevCount*<br/>
Eşitleme nesnesi için önceki sayıyı almak için bir değişkene işaret edin. NULL ise, önceki sayım döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu fonksiyon 'yıkıcı tarafından `CMultiLock`adlandırılır.

Tarafından yönetilen `Unlock` eşitleme nesnesinin kilidini açmaya `CMultiLock`çalışan ilk form. İkinci form, `Unlock` sahip olunan `CSemaphore` `CMultiLock`nesnelerin kilidini açmaya çalışır. Kilitli `CMultiLock` `CSemaphore` herhangi bir nesneye sahip değilse, işlev FALSE döndürür; aksi takdirde, TRUE döndürür. *lCount* ve *lpPrevCount* csinglelock parametreleri ile tam olarak [aynıdır::Unlock](../../mfc/reference/csinglelock-class.md#unlock). İkinci formu `Unlock` nadiren multilock durumlar için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
