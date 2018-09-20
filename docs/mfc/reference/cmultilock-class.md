---
title: CMultiLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39cde8affc84ed879ad3731cb6c18449c60498f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430858"
---
# <a name="cmultilock-class"></a>CMultiLock sınıfı

Çoklu iş parçacığı kullanan programda kaynaklara erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMultiLock
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiLock::CMultiLock](#cmultilock)|Oluşturur bir `CMultiLock` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMultiLock::IsLocked](#islocked)|Bir dizideki belirli bir eşitleme nesnesi kilitli olduğunu belirler.|
|[CMultiLock::Lock](#lock)|Eşitleme nesneleri dizisi bekler.|
|[CMultiLock::Unlock](#unlock)|Sahip olunan eşitleme nesneleri serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

`CMultiLock` bir temel sınıfa sahip değil.

Eşitleme sınıflarını kullanma [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), ve [CEvent](../../mfc/reference/cevent-class.md), ya da oluşturabileceğiniz bir `CMultiLock` veya [CSingleLock](../../mfc/reference/csinglelock-class.md)eşitleme nesneyi serbest nesnesini bekleyebilir. Kullanma `CMultiLock` kullanabileceğinizi belirli bir zamanda birden fazla nesne olduğunda. Kullanım `CSingleLock` yalnızca gerektiğinde bir kerede bir nesne üzerinde bekleyin.

Kullanılacak bir `CMultiLock` nesne, ilk beklemesi istediğiniz eşitleme nesneleri içeren bir dizi oluşturun. Ardından, arama `CMultiLock` denetimli kaynak sınıfının üye işlevinde içinde nesnesinin Oluşturucusu. Ardından çağırın [kilit](#lock) üye işlevi bir kaynak olup olmadığını belirlemek için (işareti). İse, üye işlevi geri kalanı ile devam edin. Hiçbir kaynak kullanılabilir haldeyse, zaman yayımlanması bir kaynak için belirli bir süre bekleyin veya hata döndürür. Bir kaynak kullanımını tamamlandıktan sonra ya da çağrı [kilidini](#unlock) işlevinin `CMultiLock` nesnedir izin ver veya yeniden kullanılmak üzere `CMultiLock` yok edilecek nesne.

`CMultiLock` çok sayıda iş parçacığı sahip olduğunda nesneleri faydalı `CEvent` nesneleri için yanıtlayabilir. Tümünü içeren bir dizi oluşturmak `CEvent` işaretçiler ve çağrı `Lock`. Bu olaylardan biri sinyal kadar beklenecek iş parçacığının neden olur.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CMultiLock` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMultiLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="cmultilock"></a>  CMultiLock::CMultiLock

Oluşturur bir `CMultiLock` nesne.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametreler

*ppObjects*<br/>
Beklenen için eşitleme nesneleri için işaretçiler dizisi. NULL olamaz.

*dwCount*<br/>
Nesne sayısı *ppObjects*. 0'dan büyük olmalıdır.

*bInitialLock*<br/>
Başlangıçta sağlanan nesnelerden herhangi birini erişme girişimi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, beklenen için eşitleme nesneleri dizisi oluşturduktan sonra çağrılır. Bu genellikle bir eşitleme nesneleri kullanılabilir hale gelmesi için beklemesi gereken iş parçacığı içinden çağrılır.

##  <a name="islocked"></a>  CMultiLock::IsLocked

Belirtilen nesnenin nonsignaled olup olmadığını belirler (kullanılamıyor).

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>Parametreler

*dwItem*<br/>
Dizin durumu sorgulanan nesnesine karşılık gelen nesneleri dizisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen nesnenin kilitli olursa sıfır dışı; Aksi durumda 0.

##  <a name="lock"></a>  CMultiLock::Lock

Bir veya daha fazla sağlanan eşitleme nesneleri tarafından denetlenen kaynakları erişim kazanmak için bu işlevi çağırın `CMultiLock` Oluşturucusu.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Eşitleme nesnesi kullanılabilir olması beklenecek süreyi belirtir (işareti). SONSUZ ise `Lock` döndürmeden önce nesne sinyal kadar bekler.

*bWaitForAll*<br/>
Tüm nesneler beklenen döndürmeden önce aynı anda sinyalli hale dönüşmesi olup olmadığını belirtir. FALSE ise `Lock` beklenen nesnelerin herhangi biri sinyal zaman döndürür.

*dwWakeMask*<br/>
Beklemeyi iptal etmek için izin verilen diğer koşulları belirtir. Bu parametre için kullanılabilir seçenekler tam bir listesi için bkz. [MsgWaitForMultipleObjects](/windows/desktop/api/winuser/nf-winuser-msgwaitformultipleobjects) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Varsa `Lock` döndürür - 1 başarısız olur. Başarılı olursa, aşağıdaki değerlerden birini döndürür:

- Arasında WAIT_OBJECT_0 ve WAIT_OBJECT_0 + (nesneler - 1 sayısı)

     Varsa *bWaitForAll* doğru ise, tüm nesneleri (kullanılabilir) sinyal. Varsa *bWaitForAll* yanlış, dönüş değeri - WAIT_OBJECT_0 olduğu dizin (kullanılabilir) işareti verilen nesnenin nesneler dizisi.

- WAIT_OBJECT_0 + (nesnelerin sayısı)

     Belirtilen olaya *dwWakeMask* iş parçacığının giriş sırada kullanılabilir.

- Arasında WAIT_ABANDONED_0 ve WAIT_ABANDONED_0 + (nesneler - 1 sayısı)

     Varsa *bWaitForAll* TRUE ise, tüm nesneleri sinyal ve nesnelerin en az biri olan bırakılan mutex nesnesi. Varsa *bWaitForAll* yanlış, dönüş değeri - WAIT_ABANDONED_0 olduğu dizin bekleme memnun bırakılan mutex nesnesi nesnelerin dizisi.

- WAIT_TIMEOUT

     Belirtilen zaman aşımı aralığı *dwTimeOut* olmadan başarılı bekleme süresi doldu.

### <a name="remarks"></a>Açıklamalar

Varsa *bWaitForAll* TRUE ise `Lock` tüm eşitleme nesneleri aynı anda sinyal haline hemen sonra başarıyla döndürür. Varsa *bWaitForAll* false değerine `Lock` bir veya daha fazla eşitleme nesneleri sinyal haline gelir olarak döndürür.

Varsa `Lock` belirtilen milisaniye sayısı en fazla için bekleyeceği hemen döndürülecek kuramıyor *dwTimeOut* döndürmeden önce parametresi. Varsa *dwTimeOut* sonsuzdur, `Lock` bir nesneye erişimi elde veya bir koşul içinde belirtilen kadar döndürmez *dwWakeMask* aşıldığı. Aksi takdirde `Lock` olan bir eşitleme nesnesi almak mümkün başarıyla döndürür; Aksi takdirde, bu hata döndürür.

##  <a name="unlock"></a>  CMultiLock::Unlock

Eşitleme nesnesi tarafından sahip olunan serbest `CMultiLock`.

```
BOOL Unlock();


BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Serbest bırakmak için başvuru sayısını sayar. 0'dan büyük olmalıdır. Belirtilen nesnenin sayısı, en yüksek süreyi aşmasına yol açıyorsa sayısı değiştirilmez ve işlev false değerini döndürür.

*lPrevCount*<br/>
Eşitleme nesnesi için önceki sayıyı almak için bir değişkene işaret eder. NULL ise, önceki sayısı döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağıran `CMultiLock`'s yıkıcı.

İlk formu `Unlock` tarafından yönetilen nesne eşitleme kilidini açmak çalışır `CMultiLock`. İkinci form, `Unlock` kilidini açmak çalışır `CSemaphore` tarafından sahip olunan nesneler `CMultiLock`. Varsa `CMultiLock` herhangi bulunmaz kilitli `CSemaphore` işlevi nesnesini döndürür FALSE; Aksi takdirde, TRUE döndürür. *lCount* ve *lpPrevCount* parametrelerinin tam olarak aynıdır [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). İkinci form, `Unlock` nadiren multilock durumlar için geçerlidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



