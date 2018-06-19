---
title: CCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
dev_langs:
- C++
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d6e713f6d5238d99af8f9311eb05a4b2dd39f7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353911"
---
# <a name="ccriticalsection-class"></a>CCriticalSection sınıfı
"Kritik bölüm" temsil eder — bir kaynak veya kod bölümüne erişmek için aynı anda tek bir iş parçacığı izin veren bir eşitleme nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Oluşturan bir `CCriticalSection` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|Erişim kazanmak için `CCriticalSection` nesnesi.|  
|[CCriticalSection::Unlock](#unlock)|Sürümler `CCriticalSection` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Dahili bir işaretçi alır **CRITICAL_SECTION** nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION** nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kritik bölümler, veri veya başka bir denetimli kaynak değiştirmek için aynı anda yalnızca bir iş parçacığı izin olduğunda yararlıdır. Örneğin, düğümleri bağlantılı bir listesine ekleyerek bir iş parçacığı tarafından aynı anda yalnızca izin verilecek bir işlemdir. Kullanarak bir `CCriticalSection` aynı anda tek bir iş parçacığı listesine erişebilir yalnızca bağlantılı liste denetlemek için nesne.  
  
> [!NOTE]
>  İşlevselliğini `CCriticalSection` sınıfı gerçek bir Win32 tarafından sağlanan **CRITICAL_SECTION** nesnesi.  
  
 Kritik bölümler zaman uyumu sağlayıcılar yerine kullanılır (bkz [CMutex](../../mfc/reference/cmutex-class.md)) ne zaman hızıdır kritik ve kaynak işlemi sınırlarında kullanılmaz.  
  
 Kullanmak için iki yöntem vardır bir `CCriticalSection` nesnesi: tek başına ve katıştırılmış bir sınıf.  
  
-   Tek başına kullanmak için tek başına yöntem `CCriticalSection` nesne, oluşturmak `CCriticalSection` nesne gerektiğinde. Sonra başarılı bir dönüş oluşturucusundan açıkça çağrısıyla nesneyi kilitlemek [kilit](#lock). Çağrı [Unlock](#unlock) işiniz bittiğinde kritik bölüm erişme. Bu, daha anlaşılır birisi, kaynak kodu okuma sırasında kilitlemek ve kritik bölüm önce ve sonra erişim kilidini açmak unutmamalısınız gibi daha fazla hataya yöntemidir.  
  
     Daha fazla tercih edilen bir yöntem kullanmaktır [CSingleLock](../../mfc/reference/csinglelock-class.md) sınıfı. Ayrıca sahip bir `Lock` ve `Unlock` yöntemi, ancak bir özel durum oluşursa, kaynağın kilidini açma hakkında endişelenmeniz zorunda değilsiniz.  
  
-   Ayrıca paylaşabilirsiniz bir sınıfın birden çok iş parçacığı ile ekleyerek yöntemi katıştırılmış bir `CCriticalSection`-türü veri üyesini sınıfı ve gerektiğinde veri üyesi kilitleme.  
  
 Kullanma hakkında daha fazla bilgi için `CCriticalSection` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection  
 Oluşturan bir `CCriticalSection` nesnesi.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim veya serbest bir `CCriticalSection` nesne, oluşturma bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [Unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri. Varsa `CCriticalSection` nesne kullanılan tek başına, çağrı kendi [Unlock](#unlock) üye işlevi bırakın.  
  
 Gerekli sistem belleği, bellek özel durumunu ayırmaya Oluşturucusu başarısız olursa (tür [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) otomatik olarak oluşturulur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CCriticalSection::Lock](#lock).  
  
##  <a name="lock"></a>  CCriticalSection::Lock  
 Kritik bölüm nesnesine erişim kazanmak için bu üye işlevini çağırın.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwTimeout`  
 `Lock` Bu parametre değeri yok sayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Lock` kritik bölüm nesne işaret kadar döndürmeyecektir engelleyen bir çağrısıdır (kullanılabilir olur).  
  
 Zamanlanmış bekler gerekliyse, kullanabileceğiniz bir [CMutex](../../mfc/reference/cmutex-class.md) yerine Nesne bir `CCriticalSection` nesnesi.  
  
 Varsa `Lock` gerekli sistem belleği, bellek özel durumunu ayırmaya başarısız (tür [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) otomatik olarak oluşturulur.  
  
### <a name="example"></a>Örnek  
 Bu örnek, bir paylaşılan kaynağa erişim denetleyerek iç içe geçmiş kritik bölüm yaklaşım gösterir (statik `_strShared` nesnesi) paylaşılan kullanarak `CCriticalSection` nesnesi. `SomeMethod` İşlevi gösteren bir paylaşılan kaynak güvenli bir şekilde güncelleştirme.  
  
 [!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>  CCriticalSection::m_sect  
 Tüm tarafından kullanılan bir kritik bölüm nesnesi içeren `CCriticalSection` yöntemleri.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *  
 Alır bir **CRITICAL_SECTION** nesnesi.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi iç almak için bu işlevi çağırmak **CRITICAL_SECTION** nesnesi.  
  
##  <a name="unlock"></a>  CCriticalSection::Unlock  
 Sürümler `CCriticalSection` nesne başka bir iş parçacığı tarafından kullanım için.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CCriticalSection` nesnenin iş parçacığı tarafından sahibi ve yayın başarılı; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `CCriticalSection` tek başına kullanılan `Unlock` kritik bölümü tarafından denetlenen kaynak kullanımını tamamlandıktan hemen sonra çağrılmalıdır. Varsa bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne kullanılıyor, `CCriticalSection::Unlock` kilit nesnenin tarafından çağrılacak `Unlock` üye işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMutex Sınıfı](../../mfc/reference/cmutex-class.md)
