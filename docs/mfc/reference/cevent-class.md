---
title: CEvent sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 301549e26212448ae0392a356aa556358dcf6f47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205469"
---
# <a name="cevent-class"></a>CEvent sınıfı
Başka bir olayın oluştuğunu bildirmek bir iş parçacığını etkinleştiren eşitleme nesnesi olan bir olayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CEvent : public CSyncObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEvent::CEvent](#cevent)|Oluşturur bir `CEvent` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEvent::PulseEvent](#pulseevent)|Kümeleri kullanılabilir olaya (sinyal), bekleyen iş parçacıklarının serbest bırakır ve olay için kullanılamaz (nonsignaled) ayarlar.|  
|[CEvent::ResetEvent](#resetevent)|Olay için kullanılamaz (nonsignaled) ayarlar.|  
|[CEvent::SetEvent](#setevent)|Olay için kullanılabilir (dönmesine) ayarlar ve tüm bekleyen iş parçacıklarının serbest bırakır.|  
|[CEvent::Unlock](#unlock)|Olay nesnesiyle serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir iş parçacığı görevi gerçekleştirmek ne zaman bilmeniz gerekir olayları yararlıdır. Örneğin, yeni veriler kullanılabilir olduğunda bir veri arşivine veri kopyalayan bir iş parçacığı bildirilmelidir. Kullanarak bir `CEvent` nesneyi kopyalama iş parçacığı yeni veriler kullanılabilir olduğunda iş parçacığının olabildiğince çabuk görevini gerçekleştirebilirsiniz.  
  
 `CEvent` nesnelerin iki türü vardır: elle ve otomatik.  
  
 Otomatik `CEvent` nesne en az bir iş parçacığı kullanıma sunulduktan sonra verilmemiş bir (kullanılamıyor) durumu otomatik olarak döndürür. Varsayılan olarak, bir `CEvent` nesne, geçirdiğiniz sürece otomatiktir `TRUE` için *bManualReset* oluşturma sırasında parametre.  
  
 El ile `CEvent` nesne kalır belirlediği durumunda [SetEvent](#setevent) veya [ResetEvent](#resetevent) diğer işlev çağrılana kadar. El ile oluşturmak için `CEvent` nesne, geçmesi `TRUE` için `bManualReset` oluşturma sırasında parametre.  
  
 Kullanılacak bir `CEvent` nesne, oluşturmak `CEvent` nesne gerekli olduğunda. Beklemesi ve ayrıca, uygulamanızın ilk başta bunu ait olması gerektiğini belirtmek istediğiniz olay adını belirtin. Ardından, olay Oluşturucu döndürür erişebilirsiniz. Çağrı [SetEvent](#setevent) sinyal (kullanılabilir duruma getirin) için olay nesnesi ve ardından bir çağrı [kilidini](#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.  
  
 Alternatif bir yöntem kullanarak `CEvent` türünde bir değişken eklemek için nesneleri, `CEvent` denetimine istediğiniz sınıfı için bir veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusuna çağrı `CEvent` veri üyesi olay başlangıçta işareti verilen ve ayrıca istediğiniz olay nesnesinin adı (bu süreci boyunca kullanılacaksa bu olayın benzersiz türünü belirtin sınırlar) ve tüm güvenlik öznitelikleri.  
  
 Denetlenen bir kaynağa erişmek için bir `CEvent` nesne bu şekilde, ilk iki türünde bir değişken oluşturun [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) kaynağınızın erişim yönteminde. Ardından çağırın `Lock` yöntemi nesnesi kilitlenemedi (örneğin, [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynak, kaynağın yayımlanması ve erişmek veya kaynak yayımlanacak bekleyin tamamlanmasını bekleyin, zaman aşımı erişebilir ve kaynağa erişmek başarısız. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynağı serbest bırakmak için çağrı `SetEvent` olay nesnesinin sinyal ve ardından `Unlock` yöntemi nesnesi kilitlenemedi (örneğin, [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), veya kapsam dışına düşen nesnesi kilitlenemedi.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CEvent` nesneleri bkz [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="cevent"></a>  CEvent::CEvent  
 Adlandırışmış veya adlandırılmamış bir yapıları `CEvent` nesne.  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *bInitiallyOwn*  
 TRUE ise iş parçacığı için `CMultilock` veya `CSingleLock` nesne etkinleştirilir. Aksi takdirde, kaynağa erişmek isteyen tüm iş parçacıklarının beklemeniz gerekir.  
  
 *bManualReset*  
 TRUE ise, el ile bir olay Olay nesnedir, aksi takdirde olay nesnesiyle otomatik bir olaydır belirtir.  
  
 *lpszName*  
 Adını `CEvent` nesne. İşlem sınırları ötesinde nesneye kullanılacaksa sağlanmalıdır. Oluşturucu ad var olan bir olaya eşleşiyorsa, yeni bir yapılar `CEvent` olay adının başvuran nesne. Adla eşleşen bir olay değil mevcut olan bir eşitleme nesnesi oluşturma başarısız olur. NULL ise, adı null olacaktır.  
  
 *lpsaAttribute*  
 Olay nesnesi için güvenlik öznitelikleri. Bu yapı tam bir açıklaması için bkz. [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK.  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim veya yayın için bir `CEvent` nesne, oluşturun bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri.  
  
 Durumunu değiştirmek için bir `CEvent` sinyal nesnesini (iş parçacıkları bekleyin gerek kalmaz), çağrı [SetEvent](#setevent) veya [pulseevent güvenilir](#pulseevent). Durumunu ayarlamak için bir `CEvent` nonsignaled nesnesine (iş parçacıkları gerekir beklemeniz gerekebilir), çağrı [ResetEvent](#resetevent).  
  
> [!IMPORTANT]
>  Oluşturduktan sonra `CEvent` nesnesi [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) mutex önceden yoksa emin olmak için. Mutex beklenmedik bir şekilde mevcut olması, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, tanıtıcı kapatın ve var olan bir hata varmış gibi nesnesi oluşturulurken devam etmek için önerilen güvenliğe yordam aynıdır.  
  
##  <a name="pulseevent"></a>  CEvent::PulseEvent  
 Sinyal olay durumu (kullanılabilir) olarak ayarlar, herhangi bir bekleyen iş parçacığı serbest bırakır ve kendisine nonsignaled (kullanılamıyor) otomatik olarak sıfırlar.  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Elle etkinlikse, tüm bekleyen iş parçacıklarının yayımlanan, olay için nonsignaled ayarlanır ve `PulseEvent` döndürür. Olayı otomatik ise, tek bir iş parçacığı serbest, olay için nonsignaled ayarlanır ve `PulseEvent` döndürür.  
  
 İş parçacığı bekleniyor veya iş parçacığı hemen serbest bırakılabilir `PulseEvent` olaya durumunu nonsignaled ayarlar ve döndürür.  
  
 `PulseEvent` temel alınan Win32 kullanan `PulseEvent` işlevin kısa bir süre içinde bekleme durumundan bir çekirdek modu zaman uyumsuz bir yordam çağrısı tarafından kaldırılabilir. Bu nedenle, `PulseEvent` güvenilir değil ve yeni uygulamalar tarafından kullanılmamalıdır. Daha fazla bilgi için [pulseevent güvenilir işlevi](/windows/desktop/api/winbase/nf-winbase-pulseevent).  
  
##  <a name="resetevent"></a>  CEvent::ResetEvent  
 Açıkça ayarlamak için sinyal tarafından durumu olayına kadar nonsignaled ayarlar [SetEvent](#setevent) üye işlevi.  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, bu olay beklemek için erişmek isteyen tüm iş parçacıklarının neden olur.  
  
 Bu üye işlevi, otomatik olayları tarafından kullanılmaz.  
  
##  <a name="setevent"></a>  CEvent::SetEvent  
 Herhangi bir bekleyen iş parçacığı bırakılıyor olayın sinyal için durumunu ayarlar.  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışı Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Elle etkinlikse, olay kadar sinyal kalacak [ResetEvent](#resetevent) çağrılır. Bu durumda birden fazla iş parçacığı serbest bırakılabilir. Olayı otomatik ise, tek bir iş parçacığı yayımlanana kadar olay sinyal kalır. Sistem, ardından olay durumunun nonsignaled için ayarlanır. İş parçacığı bekliyorsanız, tek bir iş parçacığı yayımlanana kadar durumu sinyal kalır.  
  
##  <a name="unlock"></a>  CEvent::Unlock  
 Olay nesnesiyle serbest bırakır.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olay nesnesiyle ve olay iş parçacığına ait sıfır olmayan bir otomatik olay; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, şu anda bunlar bitirdikten sonra nesnesi kilitlenemedi yeniden kullanılabilir ise, serbest bırakmak için otomatik olay kendi iş parçacıkları tarafından çağrılır. Kilit nesnesi değil yeniden kullanılabilir ise, bu işlev tarafından kilit nesnenin yok Edicisi çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

