---
description: 'Daha fazla bilgi edinin: CEvent sınıfı'
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
ms.openlocfilehash: 0db33c89b52c3c6cb3dbf37cb3ea3da96e6c6c71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184705"
---
# <a name="cevent-class"></a>CEvent sınıfı

Bir olayı, bir olayın gerçekleştiği başka bir iş parçacığının bilgilendirmek için izin veren bir eşitleme nesnesi olan bir olayı temsil eder.

## <a name="syntax"></a>Syntax

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

Olaylar, bir iş parçacığının görevini ne zaman gerçekleştireceğini bilmemiz gereken durumlarda faydalıdır. Örneğin, verileri bir veri arşivine kopyalayan bir iş parçacığına yeni veriler kullanılabilir olduğunda bildirilmesi gerekir. `CEvent`Yeni veriler kullanılabilir olduğunda kopya iş parçacığına bildirimde bulunan bir nesne kullanarak, iş parçacığı görevini mümkün olan en kısa sürede gerçekleştirebilir.

`CEvent` nesneler iki türe sahiptir: el ile ve otomatik.

Bir otomatik `CEvent` nesne, en az bir iş parçacığı yayımlandıktan sonra otomatik olarak, sinyal olmayan (kullanılamayan) bir duruma geri döner. Varsayılan olarak, `CEvent` `TRUE` oluşturma sırasında *bManualReset* parametresi için geçiş yapmadığınız takdirde bir nesne otomatiktir.

El ile `CEvent` nesne, diğer işlev çağrılana kadar [SetEvent](#setevent) veya [ResetEvent](#resetevent) tarafından ayarlanan durumda kalır. El ile nesne oluşturmak için `CEvent` , `TRUE` `bManualReset` oluşturma sırasında parametresini geçirin.

Bir nesne kullanmak için `CEvent` , `CEvent` gerekli olduğunda nesneyi oluşturun. Beklemek istediğiniz olayın adını belirtin ve uygulamanızın başlangıçta sahip olması gerektiğini de belirtin. Daha sonra, Oluşturucu döndüğünde olaya erişebilirsiniz. Olay nesnesini işaret etmek için [SetEvent](#setevent) çağırın (kullanılabilir hale getirin) ve ardından denetlenen kaynağa erişmeyi bitirdiğinizde [unlock](#unlock) öğesini çağırın.

Nesneleri kullanmak için alternatif bir yöntem `CEvent` , `CEvent` denetlemek istediğiniz sınıfa bir veri üyesi olarak türünde bir değişken eklemektir. Denetlenen nesnenin yapımını yaparken, `CEvent` veri üyesinin oluşturucusunu çağırın ve olayın başlangıçta döndürülüp belirtilmediğini ve ayrıca istediğiniz olay nesnesi türünü, olayın adını (işlem sınırları boyunca kullanılacaksa) ve istediğiniz güvenlik özniteliklerini belirtin.

Bir nesne tarafından denetlenen bir kaynağa `CEvent` Bu şekilde erişmek için, öncelikle kaynağınızın erişim yönteminde [CSingleLock](../../mfc/reference/csinglelock-class.md) ya da [CMultiLock](../../mfc/reference/cmultilock-class.md) türünde bir değişken oluşturun. Ardından, `Lock` Lock nesnesinin yöntemini çağırın (örneğin, [CMultiLock:: Lock](../../mfc/reference/cmultilock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını, zaman aşımına gelmesini ve kaynağa erişim kazanmasının tamamlanmasını bekler. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, `SetEvent` olay nesnesini sinyalin çağırın ve ardından `Unlock` kilit nesnesinin yöntemini kullanın (örneğin, [CMultiLock:: unlock](../../mfc/reference/cmultilock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Nesneleri kullanma hakkında daha fazla bilgi için `CEvent` bkz. [Çoklu Iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="ceventcevent"></a><a name="cevent"></a> CEvent:: CEvent

Adlandırılmış veya adlandırılmamış bir `CEvent` nesne oluşturur.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*Biniyown*<br/>
TRUE ise, veya nesnesi için iş `CMultilock` parçacığı `CSingleLock` etkindir. Aksi takdirde, kaynağa erişmek isteyen tüm iş parçacıklarının beklemesi gerekir.

*bManualReset*<br/>
TRUE ise, olay nesnesinin manuel bir olay olduğunu belirtir, aksi takdirde olay nesnesi bir otomatik olaydır.

*lpszName*<br/>
`CEvent`Nesnenin adı. Nesne, işlem sınırları genelinde kullanılacaksa, sağlanmalıdır. Ad var olan bir olayla eşleşiyorsa, Oluşturucu `CEvent` Bu adın olayına başvuran yeni bir nesne oluşturur. Ad, olay olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur. NULL ise ad null olur.

*lpsaAttribute*<br/>
Olay nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir nesneye erişmek veya onu serbest bırakmak için `CEvent` bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın.

Bir `CEvent` nesnenin durumunu sinyal olarak değiştirmek için (iş parçacıkları beklemek zorunda değildir), [SetEvent](#setevent) veya [PulseEvent](#pulseevent)çağırın. Bir `CEvent` nesnenin durumunu sinyal dışı olarak ayarlamak için (iş parçacıkları beklemesi gerekir), [ResetEvent](#resetevent)çağırın.

> [!IMPORTANT]
> Nesneyi oluşturduktan sonra `CEvent` , mutex ' [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) i kullanarak mutex 'in zaten mevcut olmadığından emin olun. Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

## <a name="ceventpulseevent"></a><a name="pulseevent"></a> CEvent::P ulseEvent

Olayın durumunu sinyal (kullanılabilir) olarak ayarlar, bekleyen iş parçacıklarını yayınlar ve sinyal dışı (kullanılamaz) otomatik olarak sıfırlar.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Olay el ile ise, bekleyen tüm iş parçacıkları serbest bırakılır, olay sinyalsiz olarak ayarlanır ve `PulseEvent` döndürür. Olay otomatiktir, tek bir iş parçacığı serbest bırakılır, olay sinyalsiz olarak ayarlanır ve `PulseEvent` döndürür.

Bekleyen iş parçacığı yoksa veya hiçbir iş parçacığı hemen yayımlanamadığında, `PulseEvent` olayın durumunu sinyalsiz ve geri dönüşler olarak ayarlar.

`PulseEvent``PulseEvent`, çekirdek modu zaman uyumsuz yordam çağrısı tarafından, bekleme durumundan geçici olarak kaldırılabilecek temel Win32 işlevini kullanır. Bu nedenle, `PulseEvent` güvenilir değildir ve yeni uygulamalar tarafından kullanılmamalıdır. Daha fazla bilgi için bkz. [PulseEvent işlevi](/windows/win32/api/winbase/nf-winbase-pulseevent).

## <a name="ceventresetevent"></a><a name="resetevent"></a> CEvent:: ResetEvent

Açıkça [SetEvent](#setevent) üye işlevi tarafından sinyal olarak ayarlanana kadar, olayın durumunu sinyal dışı olarak ayarlar.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, bu olaya erişmek isteyen tüm iş parçacıklarının beklemesini sağlar.

Bu üye işlevi otomatik olaylar tarafından kullanılmıyor.

## <a name="ceventsetevent"></a><a name="setevent"></a> CEvent:: SetEvent

Etkinliğin durumunu, bekleyen iş parçacıklarını serbest bırakarak, sinyal olarak ayarlar.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı, değilse 0.

### <a name="remarks"></a>Açıklamalar

Olay manuel ise, [ResetEvent](#resetevent) çağrılana kadar olay sinyalde kalır. Bu durumda birden fazla iş parçacığı yayımlaneklenebilir. Olay otomatiktir, tek bir iş parçacığı serbest bırakılana kadar olay sinyal olarak kalır. Sistem daha sonra olayın durumunu sinyal dışı olarak ayarlar. Bekleyen bir iş parçacığı yoksa, bir iş parçacığı serbest bırakılana kadar durum sinyal kalır.

## <a name="ceventunlock"></a><a name="unlock"></a> CEvent:: unlock

Olay nesnesini serbest bırakır.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı olay nesnesine sahipse ve olay bir otomatik olayse sıfır olmayan bir değer; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, işlem tamamlandıktan sonra, kendi kilitleme nesneleri yeniden kullanılacak şekilde serbest bir olaya sahip olan iş parçacıkları tarafından çağırılır. Kilit nesnesi yeniden kullanılmazsa, bu işlev kilit nesnesinin yıkıcısı tarafından çağrılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
