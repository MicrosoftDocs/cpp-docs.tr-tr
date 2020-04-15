---
title: CEvent Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
ms.openlocfilehash: 009a17342cb92025d67bf2fe0df1b9d5c7c0c6f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373952"
---
# <a name="cevent-class"></a>CEvent Sınıfı

Bir iş parçacığının bir olayın oluştuğunu diğerine bildirmesini sağlayan bir eşitleme nesnesi olan bir olayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CEvent : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CEvent::cEvent](#cevent)|Bir `CEvent` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEvent::PulseOlay](#pulseevent)|Olayı kullanılabilir (sinyalli) olarak ayarlar, bekleyen iş parçacıklarını serbest bırakır ve olayı kullanılamaz (sinyalsiz) olarak ayarlar.|
|[CEvent::ResetEvent](#resetevent)|Olayı kullanılamaz (sinyal siz) olarak ayarlar.|
|[CEvent::SetEvent](#setevent)|Olayı kullanılabilir (sinyalli) ayarlar ve bekleyen iş parçacıklarını serbest bırakır.|
|[CEvent::Kilidini Aç](#unlock)|Olay nesnesini serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

Olaylar, bir iş parçacığının görevini ne zaman gerçekleştireceklerini bilmesi gerektiğinde yararlıdır. Örneğin, yeni veriler kullanılabilir olduğunda verileri veri arşivine kopyalayan bir iş parçacığının bildirilmesi gerekir. Yeni veriler `CEvent` kullanılabilir olduğunda kopya iş parçacığı bildirmek için bir nesne kullanarak, iş parçacığı görevini mümkün olan en kısa sürede gerçekleştirebilir.

`CEvent`nesnelerin iki türü vardır: manuel ve otomatik.

Otomatik `CEvent` bir nesne, en az bir iş parçacığı serbest bırakıldıktan sonra otomatik olarak sinyalvermeyen (kullanılamayan) duruma geri döner. Varsayılan olarak, `CEvent` inşaat sırasında `TRUE` *bManualReset* parametresini geçmedikçe nesne otomatiktir.

El `CEvent` ile nesne, diğer işlev çağrılana kadar [SetEvent](#setevent) veya [ResetEvent](#resetevent) tarafından ayarlanan durumda kalır. El ile `CEvent` nesne oluşturmak `TRUE` için, inşaat sırasında parametre için geçirin. `bManualReset`

Bir `CEvent` nesneyi kullanmak `CEvent` için, gerektiğinde nesneyi oluşturun. Beklemek istediğiniz olayın adını belirtin ve uygulamanızın başlangıçta bu olaya sahip olması gerektiğini de belirtin. Daha sonra oluşturucu döndüğünde olaya erişebilirsiniz. Olay nesnesine sinyal vermek (kullanılabilir hale getirmek) için [SetEvent'i](#setevent) arayın ve denetlenendeki kaynağa erişmeyi bitirdiğinizde [Unlock'u](#unlock) arayın.

Nesneleri kullanmak `CEvent` için alternatif bir yöntem, denetlemek `CEvent` istediğiniz sınıfa veri üyesi olarak bir tür değişkeni eklemektir. Denetlenen nesnenin oluşturulması sırasında, veri `CEvent` üyesinin oluşturucuyu arayın ve olayın başlangıçta sinyal verilip verilmediğini belirtin ve ayrıca istediğiniz olay nesnesinin türünü, olayın adını (işlem sınırları arasında kullanılacaksa) ve istediğiniz güvenlik özniteliklerini belirtin.

Bu şekilde bir nesne `CEvent` tarafından denetlenir bir kaynağa erişmek için, önce kaynağınızın erişim yönteminde [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden veya [CMultiLock](../../mfc/reference/cmultilock-class.md) türünden bir değişken oluşturun. Ardından kilit `Lock` nesnesinin yöntemini arayın (örneğin, [CMultiLock::Lock).](../../mfc/reference/cmultilock-class.md#lock) Bu noktada, iş parçacığınız kaynağa erişebilir, kaynağın serbest bırakılmasını ve erişim kazanmasını bekler veya kaynağın serbest bırakılmasını, zaman dolmasını bekler ve kaynağa erişemeyecektir. Her durumda, kaynağınıza iş parçacığı güvenli bir şekilde erişildi. Kaynağı serbest bırakmak `SetEvent` için olay nesnesini işaretlemeyi `Unlock` ve ardından kilit nesnesinin yöntemini (örneğin, [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)) kullanın veya kilit nesnesinin kapsam dışına düşmesine izin verin.

Nesnelerin nasıl kullanılacağı `CEvent` hakkında daha fazla bilgi için bkz: Çoklu İş [Parçacığı: Eşitleme Sınıfları Nasıl Kullanılır.](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="ceventcevent"></a><a name="cevent"></a>CEvent::cEvent

Adlandırılmış veya adsız `CEvent` bir nesne oluşturuyor.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*bInitiallyOwnOwn*<br/>
TRUE ise, `CMultilock` `CSingleLock` nesnenin iş parçacığı etkinleştirilir. Aksi takdirde, kaynağa erişmek isteyen tüm iş parçacıkları nın beklemesi gerekir.

*bManualReset*<br/>
TRUE ise, olay nesnesinin el ile bir olay olduğunu belirtir, aksi takdirde olay nesnesi otomatik bir olaydır.

*Lpszname*<br/>
Nesnenin `CEvent` adı. Nesne işlem sınırları arasında kullanılacaksa sağlanmalıdır. Ad varolan bir olayla eşleşiyorsa, `CEvent` oluşturucu bu adın olayına başvuran yeni bir nesne oluşturur. Ad, olay olmayan varolan bir eşitleme nesnesi ile eşleşirse, yapı başarısız olur. NULL ise, ad null olacaktır.

*lpsaAttribute*<br/>
Olay nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK'daki [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CEvent` nesneye erişmek veya serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [kilitle](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) aç üye işlevlerini arayın.

Bir `CEvent` nesnenin durumunu sinyal (iş parçacıkları beklemek zorunda değildir) olarak değiştirmek için SetEvent veya [PulseEvent'i](#setevent) arayın. [PulseEvent](#pulseevent) Bir `CEvent` nesnenin durumunu sinyal verilmeyen (iş parçacıkları beklemeli) ayarlamak için [ResetEvent'i](#resetevent)arayın.

> [!IMPORTANT]
> Nesneyi `CEvent` oluşturduktan sonra, mutex'in zaten var olmadığından emin olmak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) kullanın. Mutex beklenmedik bir şekilde var olsaydı, bir haydut süreci çömelme olduğunu gösterebilir ve kötü niyetli mutex kullanmak niyetinde olabilir. Bu durumda, önerilen güvenlik bilinçli yordamı tutamacı kapatmak ve nesne oluştururken bir hata var gibi devam etmektir.

## <a name="ceventpulseevent"></a><a name="pulseevent"></a>CEvent::PulseOlay

Olayın durumunu sinyal (kullanılabilir) olarak ayarlar, bekleyen iş parçacıklarını serbest bırakır ve otomatik olarak sinyal sizde (kullanılamaz) sıfırlar.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Olay el ile yse, tüm bekleyen iş parçacıkları serbest bırakılır, olay `PulseEvent` sinyal verilmez olarak ayarlanır ve döndürür. Olay otomatikse, tek bir iş parçacığı serbest bırakılır, olay `PulseEvent` sinyal verilmedi ve döndürür.

Hiçbir iş parçacığı bekliyorsa veya iş parçacığı `PulseEvent` hemen serbest bırakılamazsa, olayın durumunu sinyal verilmeyen ve döndürecek şekilde ayarlar.

`PulseEvent`çekirdek modu asynchronous yordam çağrısı ile bekleme durumundan anlık olarak kaldırılabilen temel Win32 `PulseEvent` işlevini kullanır. Bu `PulseEvent` nedenle, güvenilmez ve yeni uygulamalar tarafından kullanılmamalıdır. Daha fazla bilgi için [PulseEvent işlevine](/windows/win32/api/winbase/nf-winbase-pulseevent)bakın.

## <a name="ceventresetevent"></a><a name="resetevent"></a>CEvent::ResetEvent

[SetEvent](#setevent) üye işlevi tarafından açıkça sinyal olarak ayarlanana kadar olayın durumunu sinyalsiz olarak ayarlar.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, bu olaya erişmek isteyen tüm iş parçacıklarının beklemesine neden olur.

Bu üye işlev otomatik olaylar tarafından kullanılmaz.

## <a name="ceventsetevent"></a><a name="setevent"></a>CEvent::SetEvent

Bekleyen iş parçacıklarını serbest bırakarak olayın durumunu sinyalolarak ayarlar.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

Nonzero işlevi başarılı olsaydı, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Olay el ile yapılırsa, [ResetEvent](#resetevent) çağrılana kadar olay sinyalolarak kalır. Bu durumda birden fazla iş parçacığı serbest bırakılabilir. Olay otomatikse, tek bir iş parçacığı serbest bırakılına kadar olay sinyalolarak kalır. Sistem daha sonra sinyal verilmeyen olayın durumunu ayarlar. İş parçacığı beklemiyorsa, bir iş parçacığı serbest bırakılına kadar durum sinyalolarak kalır.

## <a name="ceventunlock"></a><a name="unlock"></a>CEvent::Kilidini Aç

Olay nesnesini serbest bırakır.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Olay nesnesinin sahibi iş parçacığı ve olay otomatik bir olaysa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kilit nesnesi yeniden kullanılacaksa, şu anda otomatik bir olaya sahip olan iş parçacıkları tarafından çağrılır. Kilit nesnesi yeniden kullanılamazsa, bu işlev kilit nesnesinin yıkıcısı tarafından çağrılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
