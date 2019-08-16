---
title: CEvent sınıfı
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
ms.openlocfilehash: fbf2d834163199107aae44bd5723ceff79e36f91
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506685"
---
# <a name="cevent-class"></a>CEvent sınıfı

Bir olayı, bir olayın gerçekleştiği başka bir iş parçacığının bilgilendirmek için izin veren bir eşitleme nesnesi olan bir olayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CEvent : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CEvent:: CEvent](#cevent)|Bir `CEvent` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CEvent::P ulseEvent](#pulseevent)|Olayı kullanılabilir (sinyal) olarak ayarlar, iş parçacıklarını bekleyen yayınlar ve olayı kullanılamaz (sinyal dışı) olarak ayarlar.|
|[CEvent:: ResetEvent](#resetevent)|Olayı kullanılamaz (sinyal dışı) olarak ayarlar.|
|[CEvent:: SetEvent](#setevent)|Olayı kullanılabilir (sinyal) olarak ayarlar ve bekleyen iş parçacıklarını yayınlar.|
|[CEvent:: unlock](#unlock)|Olay nesnesini serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

Olaylar, bir iş parçacığının görevini ne zaman gerçekleştireceğini bilmemiz gereken durumlarda faydalıdır. Örneğin, verileri bir veri arşivine kopyalayan bir iş parçacığına yeni veriler kullanılabilir olduğunda bildirilmesi gerekir. Yeni veriler kullanılabilir `CEvent` olduğunda kopya iş parçacığına bildirimde bulunan bir nesne kullanarak, iş parçacığı görevini mümkün olan en kısa sürede gerçekleştirebilir.

`CEvent`nesneler iki türe sahiptir: el ile ve otomatik.

Bir otomatik `CEvent` nesne, en az bir iş parçacığı yayımlandıktan sonra otomatik olarak, sinyal olmayan (kullanılamayan) bir duruma geri döner. Varsayılan olarak, oluşturma `CEvent` sırasında *bManualReset* parametresi için `TRUE` geçiş yapmadığınız takdirde bir nesne otomatiktir.

El ile `CEvent` nesne, diğer işlev çağrılana kadar [SetEvent](#setevent) veya [ResetEvent](#resetevent) tarafından ayarlanan durumda kalır. El ile `CEvent` nesne oluşturmak için, oluşturma `TRUE` sırasında `bManualReset` parametresini geçirin.

Bir `CEvent` nesne kullanmak için, gerekli olduğunda `CEvent` nesneyi oluşturun. Beklemek istediğiniz olayın adını belirtin ve uygulamanızın başlangıçta sahip olması gerektiğini de belirtin. Daha sonra, Oluşturucu döndüğünde olaya erişebilirsiniz. Olay nesnesini işaret etmek için [SetEvent](#setevent) çağırın (kullanılabilir hale getirin) ve ardından denetlenen kaynağa erişmeyi bitirdiğinizde [unlock](#unlock) öğesini çağırın.

Nesneleri kullanmak `CEvent` için alternatif bir yöntem, denetlemek istediğiniz sınıfa bir veri üyesi `CEvent` olarak türünde bir değişken eklemektir. Denetlenen nesnenin oluşturulması sırasında, `CEvent` veri üyesinin oluşturucusunu çağırın ve olayın başlangıçta döndürülüp belirtilmediğini ve aynı zamanda istediğiniz olay nesnesi türünü, olayın adını (işlem genelinde kullanılacaksa) belirtin. sınırlar) ve istediğiniz güvenlik öznitelikleri.

Bir `CEvent` nesne tarafından denetlenen bir kaynağa bu şekilde erişmek için, öncelikle kaynağınızın erişim yönteminde [CSingleLock](../../mfc/reference/csinglelock-class.md) ya da [CMultiLock](../../mfc/reference/cmultilock-class.md) türünde bir değişken oluşturun. Ardından, lock `Lock` nesnesinin yöntemini çağırın (örneğin, [CMultiLock:: Lock](../../mfc/reference/cmultilock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını, zaman aşımına gelmesini ve kaynağa erişim kazanmasının tamamlanmasını bekler. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, olay `SetEvent` nesnesini sinyalin çağırın ve ardından kilit nesnesinin `Unlock` yöntemini kullanın (örneğin, [CMultiLock:: unlock](../../mfc/reference/cmultilock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Nesneleri kullanma `CEvent` hakkında daha fazla bilgi için bkz [. çoklu iş parçacığı: Eşitleme sınıflarını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)kullanma.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

##  <a name="cevent"></a>CEvent:: CEvent

Adlandırılmış veya adlandırılmamış `CEvent` bir nesne oluşturur.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*Biniyown*<br/>
TRUE ise, `CMultilock` veya `CSingleLock` nesnesi için iş parçacığı etkindir. Aksi takdirde, kaynağa erişmek isteyen tüm iş parçacıklarının beklemesi gerekir.

*bManualReset*<br/>
TRUE ise, olay nesnesinin manuel bir olay olduğunu belirtir, aksi takdirde olay nesnesi bir otomatik olaydır.

*lpszName*<br/>
`CEvent` Nesnenin adı. Nesne, işlem sınırları genelinde kullanılacaksa, sağlanmalıdır. Ad var olan bir olayla eşleşiyorsa, Oluşturucu bu adın olayına başvuran yeni `CEvent` bir nesne oluşturur. Ad, olay olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur. NULL ise ad null olur.

*lpsaAttribute*<br/>
Olay nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CEvent` nesneye erişmek veya onu serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın.

Bir `CEvent` nesnenin durumunu sinyal olarak değiştirmek için (iş parçacıkları beklemek zorunda değildir), [SetEvent](#setevent) veya [PulseEvent](#pulseevent)çağırın. Bir `CEvent` nesnenin durumunu sinyal dışı olarak ayarlamak için (iş parçacıkları beklemesi gerekir), [ResetEvent](#resetevent)çağırın.

> [!IMPORTANT]
>  Nesneyi oluşturduktan sonra, mutex ' i kullanarak mutex 'in zaten mevcut olmadığından emin olun. [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) `CEvent` Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

##  <a name="pulseevent"></a>CEvent::P ulseEvent

Olayın durumunu sinyal (kullanılabilir) olarak ayarlar, bekleyen iş parçacıklarını yayınlar ve sinyal dışı (kullanılamaz) otomatik olarak sıfırlar.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Olay el ile ise, bekleyen tüm iş parçacıkları serbest bırakılır, olay sinyalsiz olarak ayarlanır ve `PulseEvent` döndürür. Olay otomatiktir, tek bir iş parçacığı serbest bırakılır, olay sinyalsiz olarak ayarlanır ve `PulseEvent` döndürür.

Bekleyen iş parçacığı yoksa veya hiçbir iş parçacığı hemen yayımlanamadığında, `PulseEvent` olayın durumunu sinyalsiz ve geri dönüşler olarak ayarlar.

`PulseEvent`, çekirdek modu zaman `PulseEvent` uyumsuz yordam çağrısı tarafından, bekleme durumundan geçici olarak kaldırılabilecek temel Win32 işlevini kullanır. Bu nedenle `PulseEvent` , güvenilir değildir ve yeni uygulamalar tarafından kullanılmamalıdır. Daha fazla bilgi için bkz. [PulseEvent işlevi](/windows/win32/api/winbase/nf-winbase-pulseevent).

##  <a name="resetevent"></a>CEvent:: ResetEvent

Açıkça [SetEvent](#setevent) üye işlevi tarafından sinyal olarak ayarlanana kadar, olayın durumunu sinyal dışı olarak ayarlar.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, bu olaya erişmek isteyen tüm iş parçacıklarının beklemesini sağlar.

Bu üye işlevi otomatik olaylar tarafından kullanılmıyor.

##  <a name="setevent"></a>CEvent:: SetEvent

Etkinliğin durumunu, bekleyen iş parçacıklarını serbest bırakarak, sinyal olarak ayarlar.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı, değilse 0.

### <a name="remarks"></a>Açıklamalar

Olay manuel ise, [ResetEvent](#resetevent) çağrılana kadar olay sinyalde kalır. Bu durumda birden fazla iş parçacığı yayımlaneklenebilir. Olay otomatiktir, tek bir iş parçacığı serbest bırakılana kadar olay sinyal olarak kalır. Sistem daha sonra olayın durumunu sinyal dışı olarak ayarlar. Bekleyen bir iş parçacığı yoksa, bir iş parçacığı serbest bırakılana kadar durum sinyal kalır.

##  <a name="unlock"></a>CEvent:: unlock

Olay nesnesini serbest bırakır.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı olay nesnesine sahipse ve olay bir otomatik olayse sıfır olmayan bir değer; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, işlem tamamlandıktan sonra, kendi kilitleme nesneleri yeniden kullanılacak şekilde serbest bir olaya sahip olan iş parçacıkları tarafından çağırılır. Kilit nesnesi yeniden kullanılmazsa, bu işlev kilit nesnesinin yıkıcısı tarafından çağrılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
