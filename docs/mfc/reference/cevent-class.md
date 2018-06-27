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
ms.openlocfilehash: 8450f4b4105f5302750ea0f369d0e6c1dc2925ab
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950891"
---
# <a name="cevent-class"></a>CEvent sınıfı
Başka bir olayın oluştuğunu bildirmek bir iş parçacığı sağlayan bir eşitleme nesnesi olan bir olayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CEvent : public CSyncObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEvent::CEvent](#cevent)|Oluşturan bir `CEvent` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEvent::PulseEvent](#pulseevent)|Kümeleri kullanılabilir olayı (işaret), bekleyen iş parçacıklarının serbest bırakır ve olay (nonsignaled) ayarlar kullanılamaz.|  
|[CEvent::ResetEvent](#resetevent)|Olay kullanılamaz (nonsignaled) ayarlar.|  
|[CEvent::SetEvent](#setevent)|Olay için kullanılabilir (iş) ayarlar ve tüm bekleyen iş parçacıklarının serbest bırakır.|  
|[CEvent::Unlock](#unlock)|Olay nesnesi serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir iş parçacığı, görevi gerçekleştirmek ne zaman bilmelisiniz olduğunda olayları yararlıdır. Örneğin, yeni veriler kullanılabilir olduğunda, bir veri arşivine verileri kopyalayan bir iş parçacığı bildirilmelidir. Kullanarak bir `CEvent` yeni veriler kullanılabilir olduğunda kopyalama iş parçacığı bildirmek için nesnenin iş parçacığı mümkün olan en kısa sürede görevini gerçekleştirebilirsiniz.  
  
 `CEvent` nesnelerinin iki tür vardır: elle ve otomatik.  
  
 Otomatik `CEvent` nesne en az bir iş parçacığı yayımlandıktan sonra işareti olmayan bir (kullanılamaz) durumu otomatik olarak döndürür. Varsayılan olarak, bir `CEvent` nesne, geçirdiğiniz sürece otomatiktir `TRUE` için *bManualReset* oluşturma sırasında parametre.  
  
 El ile `CEvent` nesnesi tarafından belirlenen durumda kalır [SetEvent](#setevent) veya [ResetEvent](#resetevent) diğer işlevi çağrılıncaya kadar. El ile oluşturmak için `CEvent` nesne, geçirmek `TRUE` için `bManualReset` oluşturma sırasında parametre.  
  
 Kullanılacak bir `CEvent` nesne, oluşturmak `CEvent` nesne gerekli olduğunda. Beklemesi ve ayrıca, uygulamanızın başlangıçta ait olduğu belirtmek istediğiniz olay adını belirtin. Olay Oluşturucusu döndürüldüğünde daha sonra erişebilirsiniz. Çağrı [SetEvent](#setevent) sinyal (kullanıma) için olay nesnesi ve ardından arama [Unlock](#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.  
  
 Kullanmak için alternatif bir yöntem `CEvent` nesnedir türünde bir değişken eklemek için `CEvent` denetimine istediğiniz sınıfı veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusunun çağrı `CEvent` veri üyesi olay başlangıçta işareti verilen ve ayrıca istediğiniz olay nesnesi (Bu işlem kullanılacaksa, olayın adı benzersiz türünü belirtin sınırları) ve istediğiniz diğer güvenlik öznitelikleri.  
  
 Tarafından denetlenen bir kaynağa erişmek için bir `CEvent` nesne bu şekilde, ilk ya da türünde bir değişken oluşturmak [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) , kaynağın erişim yöntemi. ' I çağırın `Lock` kilit nesnesinin yöntemi (örneğin, [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynak, yayımlanması ve erişmek veya kaynak yayımlanacak bekleyin kaynak için bekleme zaman aşımı erişmek ve kaynağa erişmek başarısız. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynak serbest bırakmak için arama `SetEvent` olay nesnesi sinyal ve daha sonra kullanmak için `Unlock` kilit nesnesinin yöntemi (örneğin, [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), ya da kapsamı dışında kalan kilit nesnesi sağlar.  
  
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
 Adlandırılmış veya adlandırılmamış oluşturur `CEvent` nesnesi.  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *bInitiallyOwn*  
 Varsa **TRUE**, iş parçacığı `CMultilock` veya `CSingleLock` nesne etkindir. Aksi takdirde kaynağa erişmek isteyen tüm iş parçacıklarının beklemeniz gerekir.  
  
 *bManualReset*  
 Varsa **doğru**, olay nesnesi el ile bir olaydır, aksi takdirde olay nesnesi otomatik bir olaydır belirtir.  
  
 *lpszName*  
 Adını `CEvent` nesnesi. Nesne işlem sınırlarında kullanılacaksa sağlanmalıdır. Oluşturucusu adı olan bir olaya eşleşirse, yeni derlemeler `CEvent` olay adının başvuruda bulunan nesne. Bir olay değil varolan bir eşitleme nesnesi adıyla eşleşen oluşturma başarısız olur. Varsa **NULL**, adı boş olacaktır.  
  
 *lpsaAttribute*  
 Olay nesnesi için güvenlik öznitelikler. Bu yapı tam bir açıklaması için bkz: [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim veya serbest bir `CEvent` nesne, oluşturma bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [Unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri.  
  
 Durumu değiştirmek için bir `CEvent` işaret nesnesine (iş parçacıkları zorunda değilsiniz bekleyin), çağrı [SetEvent](#setevent) veya [PulseEvent](#pulseevent). Durumunu ayarlamak için bir `CEvent` nonsignaled nesnesine (iş parçacıkları gerekir bekleyin), çağrı [ResetEvent](#resetevent).  
  
> [!IMPORTANT]
>  Oluşturduktan sonra `CEvent` nesne, kullanın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) mutex önceden yoksa emin olmak için. Mutex beklenmedik bir şekilde yoksa, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, önerilen güvenliğe tanıtıcı kapatın ve gibi varsa bir hata nesnesi oluşturulurken devam etmek için bir yordamdır.  
  
##  <a name="pulseevent"></a>  CEvent::PulseEvent  
 Sinyal Olayı durumunu (kullanılabilir) ayarlar, tüm bekleyen iş parçacıklarının serbest bırakır ve kendisine nonsignaled (kullanılamaz) otomatik olarak sıfırlar.  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Olay el ile ise, tüm bekleyen iş parçacıklarının yayımlanan, olay çok nonsignaled ayarlanır ve `PulseEvent` döndürür. Olayı otomatik ise, tek bir iş parçacığı yayımlanan, olay çok nonsignaled ayarlanır ve `PulseEvent` döndürür.  
  
 İş parçacığı bekleniyor ya da iş parçacığı hemen serbest bırakılabilir `PulseEvent` olaya durumunu nonsignaled ayarlar ve döndürür.  
  
 `PulseEvent` temel alınan Win32 kullanan `PulseEvent` kısa bir süre içinde bir çekirdek modu zaman uyumsuz yordam çağrısı tarafından bekleme durumundan kaldırılabilir işlevi. Bu nedenle, `PulseEvent` güvenilir olmayan ve yeni uygulamalar tarafından kullanılmamalıdır. Daha fazla bilgi için bkz: [PulseEvent işlevi](http://msdn.microsoft.com/library/windows/desktop/ms684914).  
  
##  <a name="resetevent"></a>  CEvent::ResetEvent  
 Açıkça tarafından için iş ayarlamak için olay durumunu kadar nonsignaled ayarlar [SetEvent](#setevent) üye işlevi.  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, tüm iş parçacıklarının beklemek için bu olay erişmek isteyen neden olur.  
  
 Bu üye işlevi otomatik olaylar tarafından kullanılmaz.  
  
##  <a name="setevent"></a>  CEvent::SetEvent  
 Tüm bekleyen iş parçacığı bırakılıyor işaret için olay durumunu ayarlar.  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Olay el ile ise, olay kadar iş kalacak [ResetEvent](#resetevent) olarak adlandırılır. Bu durumda birden çok iş parçacığı serbest bırakılabilir. Olayı otomatik ise, tek bir iş parçacığı serbest kadar olay iş kalır. Sistem, ardından olayın durumu için nonsignaled ayarlarsınız. İş parçacığı bekleyen varsa, bir iş parçacığı serbest kadar durumu iş kalır.  
  
##  <a name="unlock"></a>  CEvent::Unlock  
 Olay nesnesi serbest bırakır.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı olay nesnesi ve olay sahibi sıfır olmayan bir otomatik olay; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu şu anda bunlar tamamladıktan sonra bunların kilit nesnesi yeniden kullanılabilir ise, serbest bırakmak için bir otomatik olay kendi iş parçacıkları tarafından çağrılır. Kilit nesnesi yeniden varsa bu işlev kilit nesnenin yıkıcı tarafından çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

