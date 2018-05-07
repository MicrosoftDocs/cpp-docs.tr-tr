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
ms.openlocfilehash: b5c5424018c3863ce64435bcc09d2d539560285e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmultilock-class"></a>CMultiLock sınıfı
Birden çok iş parçacıklı programda kaynaklara erişimi denetlemek kullanılan erişim denetim mekanizmasını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|Oluşturan bir `CMultiLock` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|Dizideki belirli eşitleme nesnesi kilitliyse belirler.|  
|[CMultiLock::Lock](#lock)|Eşitleme nesneler dizisi bekler.|  
|[CMultiLock::Unlock](#unlock)|Tüm ait eşitleme nesneleri serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMultiLock` bir taban sınıfı yok.  
  
 Eşitleme sınıflarını kullanma [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), ve [CEvent](../../mfc/reference/cevent-class.md), ya da oluşturabileceğiniz bir **CMultiLock** veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne beklemesi ve eşitleme nesnesi serbest bırakın. Kullanmak **CMultiLock** belirli bir zamanda kullanabileceğinizi birden fazla nesne olduğunda. Kullanım `CSingleLock` yalnızca gerektiğinde bir nesne üzerinde aynı anda beklenecek.  
  
 Kullanılacak bir **CMultiLock** nesne, önce beklemesi istediğiniz eşitleme nesnelerinin bir dizisi oluşturun. Ardından, çağrı **CMultiLock** denetimli kaynağın sınıfında üye işlevi içinde nesnenin oluşturucusu. ' I çağırın [kilit](#lock) bir kaynak olup olmadığını belirlemek için üye işlevi (işaret). İse, üye işlevini geri kalanı ile devam edin. Bir kaynak olup olmadığını zaman serbest bırakılacak bir kaynak için belirtilen miktarı bekleyin ya da hata döndürür. Bir kaynak kullanımını tamamlandıktan sonra ya da çağrısı [Unlock](#unlock) , işlev **CMultiLock** nesnesidir izin ver veya yeniden kullanılmak üzere **CMultiLock** yok edilmesi için nesne.  
  
 **CMultiLock** bir iş parçacığı çok sayıda olduğunda nesneleri en yararlı `CEvent` nesneleri yanıt vermesi için. Tümünü içeren bir dizi oluşturmak `CEvent` işaretçiler ve çağrı `Lock`. Bu, iş parçacığı olaylardan biri işaret kadar beklemeniz neden olur.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için **CMultiLock** nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CMultiLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="cmultilock"></a>  CMultiLock::CMultiLock  
 Oluşturan bir **CMultiLock** nesnesi.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppObjects`  
 Beklenen için eşitleme nesnelerine işaretçiler dizisi. Olamaz **NULL**.  
  
 `dwCount`  
 Nesnelerin sayısı `ppObjects`. 0'dan büyük olmalıdır.  
  
 `bInitialLock`  
 Başlangıçta sağlanan nesnelerden herhangi birini erişme girişimi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, beklenen için eşitleme nesneler dizisi oluşturduktan sonra çağrılır. Bu genellikle bir kullanılabilir hale gelmesi eşitleme nesneleri için beklemesi gereken iş parçacığı içinde çağrılır.  
  
##  <a name="islocked"></a>  CMultiLock::IsLocked  
 Belirtilen nesne nonsignaled olup olmadığını belirler (kullanılamaz).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwItem*  
 Durumu sorgulanan nesnesine karşılık gelen nesnelerin dizisindeki dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen nesne kilitliyse sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="lock"></a>  CMultiLock::Lock  
 Bir veya daha fazla için sağlanan eşitleme nesneleri tarafından denetlenen kaynaklara erişmek için bu işlevi çağırmak **CMultiLock** Oluşturucusu.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwTimeOut*  
 Eşitleme nesnenin kullanılabilir olması için beklenecek süreyi belirtir (işaret). Varsa **SONSUZ**, `Lock` nesne döndürmeden önce işaret kadar bekler.  
  
 `bWaitForAll`  
 Beklenen tüm nesneler, aynı anda dönmeden önce işaret hale olup olmadığını belirtir. Varsa **FALSE**, `Lock` beklenen nesnelerin herhangi biri işaret zaman döndürür.  
  
 `dwWakeMask`  
 Beklemeyi iptal etmek için kullanılabilir diğer koşulları belirtir. Bu parametre için kullanılabilir seçenekleri tam bir listesi için bkz: [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa `Lock` döndürdüğü - 1 başarısız olur. Başarılı olursa, aşağıdaki değerlerden birini döndürür:  
  
-   Arasında **WAIT_OBJECT_0** ve **WAIT_OBJECT_0** + (nesne - 1 sayısı)  
  
     Varsa `bWaitForAll` olan **doğru**, tüm nesneler (kullanılabilir) sinyal. Varsa `bWaitForAll` olan **FALSE**, dönüş değeri - **WAIT_OBJECT_0** işareti nesnenin nesneler dizisi dizininde () kullanılabilir.  
  
- **WAIT_OBJECT_0** + (nesne sayısı)  
  
     Belirtilen bir olay `dwWakeMask` iş parçacığının giriş sırada kullanılabilir.  
  
-   Arasında **WAIT_ABANDONED_0** ve **WAIT_ABANDONED_0** + (nesne - 1 sayısı)  
  
     Varsa `bWaitForAll` olan **doğru**, tüm nesneleri işaret ve nesneleri en az biri olan bir bırakılan mutex nesne. Varsa `bWaitForAll` olan **FALSE**, dönüş değeri - **WAIT_ABANDONED_0** bekleme memnun bırakılan mutex nesnesinin nesnelerin dizisindeki dizini.  
  
- **WAIT_TIMEOUT**  
  
     Belirtilen zaman aşımı aralığı *dwTimeOut* olmadan başarılı bekleme süresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bWaitForAll` olan **TRUE**, `Lock` tüm eşitleme nesneleri aynı anda işaret hale hemen başarıyla döndürür. Varsa `bWaitForAll` olan **FALSE**, `Lock` bir veya daha fazla eşitleme nesneleri işaret hale hemen döndürür.  
  
 Varsa `Lock` hemen belirtilen milisaniye sayısı en çok için bekleyeceği iade edilemiyor *dwTimeOut* dönmeden önce parametresi. Varsa *dwTimeOut* olan **SONSUZ**, `Lock` bir nesneye erişimi kazanılan veya bir koşul içinde belirtilen kadar döndürmeyecektir `dwWakeMask` aşıldığı. Aksi halde, eğer `Lock` edildi mümkün eşitleme nesnesi edinmek, onu başarıyla döndürür; Aksi takdirde, bu hata döndürür.  
  
##  <a name="unlock"></a>  CMultiLock::Unlock  
 Sahibi eşitleme nesnesi serbest `CMultiLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCount`  
 Serbest bırakmak için başvuru sayısını sayar. 0'dan büyük olmalıdır. Belirtilen süre nesnenin sayısı maksimum değerini aşmasına neden olur, count değiştirilmez ve işlevi döndürür **FALSE**.  
  
 `lPrevCount`  
 Eşitleme nesnesi için önceki sayıyı almak için bir değişken noktalarına. Varsa **NULL**, önceki sayısı alınmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından çağrılır `CMultiLock`'s yıkıcı.  
  
 İlk biçimini `Unlock` tarafından yönetilen eşitleme nesnenin kilidini açma girişiminde `CMultiLock`. İkinci biçiminde `Unlock` kilidini açma girişiminde `CSemaphore` tarafından sahip olunan nesneler `CMultiLock`. Varsa `CMultiLock` herhangi kendisine değil kilitli `CSemaphore` nesnesi, işlevi döndürür **FALSE**; Aksi takdirde döndürdüğü **TRUE**. `lCount` ve `lpPrevCount` parametrelerinin tam olarak aynıdır [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). İkinci biçiminde `Unlock` nadiren multilock durumlar için geçerlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



