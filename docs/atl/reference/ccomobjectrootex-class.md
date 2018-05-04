---
title: İn uygulamasına sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b147f0ad3f1a54c2ae640b6bf2426bcddf060b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectrootex-class"></a>İn uygulamasına sınıfı
Bu sınıf, nesne başvuru sayısı Yönetimi toplanmayan ve toplanan nesneleri işlemek için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Parametreler  
 `ThreadModel`  
 İstenen iş parçacığı modeli, yöntemleri uygulamak sınıfı. İş parçacığı modelini ayarlayarak açıkça seçebilirsiniz `ThreadModel` için [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Ayarlayarak sunucunun varsayılan iş parçacığı modeli kabul edebilir `ThreadModel` için [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Oluşturucu.|  
|[Internaladdref](#internaladdref)|Toplanmayan nesne başvurusu sayısını artırır.|  
|[Internalrelease](#internalrelease)|Başvuru sayım toplanmayan bir nesne için azaltır.|  
|[kilitleme](#lock)|İş parçacığı modeli birden çok iş parçacıklı ise, kritik bölüm nesnenin sahipliğini alır.|  
|[kilidini aç](#unlock)|İş parçacığı modeli birden çok iş parçacıklı ise, kritik bölüm nesnenin sahipliğini serbest bırakır.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase yöntemleri  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|Sınıfınızda, nesneye gerekli başlatılmasını gerçekleştirmek için geçersiz kılar.|  
|[FinalRelease](#finalrelease)|Sınıfınızda, nesneye gerekli temizleme gerçekleştirmek için geçersiz kılar.|  
|[OuterAddRef](#outeraddref)|Bir toplu nesne başvurusu sayısını artırır.|  
|[OuterQueryInterface](#outerqueryinterface)|Dış temsilcileri **IUnknown** toplanmış nesnenin.|  
|[OuterRelease](#outerrelease)|Başvuru sayım toplanmış olan bir nesne için azaltır.|  
  
### <a name="static-functions"></a>Statik işlevler  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|İçin temsilciler **IUnknown** toplanmayan bir nesne.|  
|[ObjectMain](#objectmain)|Modül başlatma ve sonlandırma nesne eşleme içinde listelenen türetilen sınıflar için sırasında çağrılan.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|İle `m_pOuterUnknown`, UNION parçası. Nesne başvuru sayısı tutacak toplanmaz çağrılırken `AddRef` ve **sürüm**.|  
|[m_pOuterUnknown](#m_pouterunknown)|İle `m_dwRef`, UNION parçası. Dış bilinmeyen bir işaretçi tutacak nesne hesaplanırken kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectRootEx` Nesne başvuru sayısı Yönetimi toplanmayan ve toplanan nesneler için işler. Nesnenizin değil toplanmakta ve nesnenizin toplanır varsa işaretçinin dış bilinmeyen tutan nesne başvurusu sayısı tutar. Toplanan nesneler için `CComObjectRootEx` yöntemleri oluşturmak için iç nesneyi başarısızlığını işlemek için kullanılabilir ve dış iç arabirimleri yayımlandığında silinmeye karşı veya iç nesneyi korumak için silinir.  
  
 COM sunucusu uygulayan bir sınıf öğesinden devralmalıdır `CComObjectRootEx` veya [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Sınıf tanımı belirtiyorsa [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) makrosu, ATL bir örneğini oluşturur **CComPolyObject\<CYourClass >** zaman **IClassFactory:: CreateInstance** olarak adlandırılır. Oluşturma sırasında dış bilinmeyen değerini denetlenir. Eğer öyleyse **NULL**, **IUnknown** toplanmayan bir nesne için uygulanır. Dış bilinmeyen değilse **NULL**, **IUnknown** toplanmış olan bir nesne için uygulanır.  
  
 Sınıfınızda belirttiğini `DECLARE_POLY_AGGREGATABLE` makrosu, ATL bir örneğini oluşturur **CAggComObject\<CYourClass >** toplanmış nesneler veya bir örneği için **CComObject\<CYourClass >** toplanmayan nesneler için.  
  
 Kullanmanın avantajı `CComPolyObject` her ikisi de zorunda kalmamak olan `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesini işleme her iki durumda. Bu nedenle, yalnızca bir kopyasını vtable ve işlevlerin bir kopya, modülünde mevcut. Vtable büyükse, bu modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesne için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.  
  
 Nesnenizin toplanır, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) tarafından uygulanan `CComAggObject` veya `CComPolyObject`. Bu sınıfların temsilci `QueryInterface`, `AddRef`, ve **sürüm** çağrılar `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, ve `OuterRelease` dış bilinmeyen iletmek için. Genellikle, kılmanız `CComObjectRootEx::FinalConstruct` hiçbir toplanmış nesneleri oluşturmak ve geçersiz kılmak için sınıfınızda `CComObjectRootEx::FinalRelease` herhangi boşaltmak için nesneleri toplanır.  
  
 Nesnenizin toplanmaz, **IUnknown** tarafından uygulanan `CComObject` veya `CComPolyObject`. Bu durumda, çağrılar `QueryInterface`, `AddRef`, ve **sürüm** için temsilci `CComObjectRootEx`'s `InternalQueryInterface`, `InternalAddRef`, ve `InternalRelease` gerçek işlemleri gerçekleştirmek için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx  
 Oluşturucu başvuru sayısı 0 başlatır.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct  
 Nesne için gereken başlatılmasını gerçekleştirmek için türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş `S_OK` başarı veya standart hata birinde `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CComObjectRootEx::FinalConstruct` yalnızca döndürür `S_OK`.  
  
 Başlatma gerçekleştirmenin avantajları vardır `FinalConstruct` , sınıf yerine:  
  
-   Bir durum kodu oluşturucudan döndüremez, ancak geri dönebilirsiniz bir `HRESULT` yoluyla `FinalConstruct`ın dönüş değeri. Sınıfının nesneleri ATL tarafından sağlanan standart üreteci kullanarak oluşturulurken, bu dönüş değeri ile ayrıntılı hata bilgileri vermenizi sağlayan COM istemcisi yayılır.  
  
-   Öğesinden bir sınıf sanal işlev mekanizması aracılığıyla sanal işlevler çağrılamaz. Bu noktada devralma hiyerarşisinde tanımlandığı gibi bir sınıf oluşturucudan sanal işlev çağırma işlevi statik olarak çözümlenmiş çağrısı sonuçlanır. Saf sanal işlev çağrıları bağlayıcı hatalara yol.  
  
     Sınıfınızda en çok türetilen sınıf devralma hiyerarşisi içinde değil — bazı işlevlerini sağlamak için ATL tarafından sağlanan türetilmiş bir sınıf kullanır. Bu sınıfı (sınıfının nesneleri diğer nesnelerin araya gerektiğinde bu kesinlikle geçerlidir) tarafından sağlanan özellikleri kullanmak için başlatma gereken şansı yoktur, ancak sınıfınızın oluşturucuda bu özelliklere erişmek için hiçbir yolu yoktur. En çok türetilen sınıfı tam olarak oluşturulan önce sınıfınız yapım kodunu yürütülür.  
  
     Ancak, `FinalConstruct` en çok türetilen sonra sınıfı tam sanal işlevleri çağırmak ve ATL tarafından sağlanan başvuru sayımı uygulama kullanmanıza olanak sağlayan oluşturulan hemen çağrılır  
  
### <a name="example"></a>Örnek  
 Genellikle, türetilmiş sınıf bu yöntemi geçersiz kılın `CComObjectRootEx` nesneleri herhangi oluşturmak için bir araya getirilir. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 Oluşturma başarısız olursa bir hata döndürebilir. Makro de kullanabilirsiniz [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) dış nesnenizin olması korumak için oluşturma sırasında iç toplanmış nesne başvuru sayısı sonra azaltır 0 sayısını artırır, silindi.  
  
 Bir toplama oluşturmak için tipik bir yol da şudur:  
  
-   Ekleme bir **IUnknown** işaretçi sınıfınıza nesne ve ona başlatma **NULL** oluşturucuda.  
  
-   Geçersiz kılma `FinalConstruct` toplama oluşturmak için.  
  
-   Kullanım **IUnknown** tanımlanan parametre olarak işaretçi [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) makrosu.  
  
-   Geçersiz kılma `FinalRelease` yayımlamayı **IUnknown** işaretçi.  
  
##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease  
 Nesne için gereken tüm temizleme işlemini yapmak için türetilmiş sınıf içinde bu yöntemin üzerine yazabilir.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CComObjectRootEx::FinalRelease` hiçbir şey yapmaz.  
  
 Temizleme gerçekleştirme `FinalRelease` nesne hala tam olarak hangi noktada adresindeki oluşturulan beri kod sınıfınız yıkıcı için ekleme için tercih edilir `FinalRelease` olarak adlandırılır. Bu, en çok türetilen sınıfı tarafından sağlanan yöntemleri güvenle erişmenize olanak tanır. Bu özellikle toplanmış tüm nesneleri silme önce serbest bırakma için önemlidir.  
  
##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef  
 Toplanmayan nesne başvuru sayısı 1 ile artırır.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı ve test olabilir bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığı modeli birden çok iş parçacıklı, ise, **InterlockedIncrement** birden çok iş parçacığı aynı anda başvuru sayısı değiştirmesini engellemek için kullanılır.  
  
##  <a name="internalqueryinterface"></a>  CComObjectRootEx::InternalQueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pThis`  
 [in] COM eşlemesi maruz arabirimleri içeren nesneyi gösteren bir işaretçi `QueryInterface`.  
  
 `pEntries`  
 [in] Bir işaretçi **_ATL_INTMAP_ENTRY** kullanılabilir arabirimleri haritasını erişen yapısı.  
  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppvObject`  
 [out] Belirtilen arabirim işaretçisi gösteren bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 `InternalQueryInterface` Yalnızca COM eşleme tablosu arabirimlerde işler. Nesnenizin toplanır, `InternalQueryInterface` dış bilinmeyen temsilci değil. Makro COM harita tabloya arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.  
  
##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease  
 Azaltır başvurusu, 1 ile toplanmayan bir nesne sayısı.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde her ikisi de olmayan-hata ayıklama ve hata ayıklama derlemeleri, bu işlevi kullanışlı Diagnostics veya test olabilen bir değer döndürür. Başvuru sayısı olması, tam değer döndürdü kullanıldığında, işletim sistemi gibi birçok faktöre bağlıdır ve olabilir veya olmayabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığı modeli birden çok iş parçacıklı, ise, **InterlockedDecrement** birden çok iş parçacığı aynı anda başvuru sayısı değiştirmesini engellemek için kullanılır.  
  
##  <a name="lock"></a>  CComObjectRootEx::Lock  
 İş parçacığı modeli birden çok iş parçacıklı ise, bu yöntem Win32 API işlevi çağırır [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), iş parçacığı kritik bölüm nesnenin sahipliğini alabilir kadar hangi bekler elde özel veri üyesi.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı kod yürütme tamamlandığında, iş parçacığı çağırmalısınız `Unlock` kritik bölüm sahipliğini serbest bırakmak için.  
  
 İş parçacığı modeli tek iş parçacıklı ise, bu yöntem hiçbir şey yapmaz.  
  
##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef  
 Dört bayt bellek erişen UNION parçası.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle `m_pOuterUnknown`, UNION parçası:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Nesne toplanmaz, başvuru sayımı erişilen `AddRef` ve **sürüm** depolanan `m_dwRef`. Nesne toplanır, dış bilinmeyen işaretçisine depolanan [m_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown  
 Dört bayt bellek erişen UNION parçası.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>Açıklamalar  
 İle `m_dwRef`, UNION parçası:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Nesne toplanır, dış bilinmeyen işaretçisine depolanan `m_pOuterUnknown`. Nesne toplanmaz, başvuru sayımı erişilen `AddRef` ve **sürüm** depolanan [m_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain  
 Listelenen her sınıf için [nesne eşlemesi](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), ne zaman modülü başlatıldıktan sonra bu işlev çağrılır ve yeniden zaman sonlandırılır.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Parametreler  
 `bStarting`  
 [out] Değer **true** sınıfı, başlatılmış aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri `bStarting` parametresi gösterir modülü yüklenmekte olan başlatılmamış veya sonlandırıldı. Varsayılan uygulaması `ObjectMain` hiçbir şey yapmaz, ancak sınıfınızda başlatmak veya sınıfı için ayırmak istediğiniz kaynakları temizlemek için bu işlevi geçersiz kılabilirsiniz. Unutmayın `ObjectMain` sınıfın tüm örnekleri istenen önce çağrılır.  
  
 `ObjectMain` Giriş noktası işlevi gerçekleştirebilir işlemi türünü kısıtlı olacak şekilde DLL giriş noktasından adı verilir. Bu kısıtlamaları hakkında daha fazla bilgi için bkz: [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) ve [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef  
 Dış bilinmeyen bir toplama başvuru sayısını artırır.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı ve test olabilir bir değer.  
  
##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface  
 İstenen arabirim dolaylı bir işaretçi alır.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppvObject`  
 [out] Belirtilen arabirim işaretçisi gösteren bir işaretçi `iid`, veya **NULL** toplama arabirimi desteklemiyorsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease  
 Azaltır bir toplama dış bilinmeyen başvuru sayısı.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olmayan hata ayıklama derlemelerinde, her zaman 0 döndürür. Hata ayıklama derlemelerinde tanılama için kullanışlı veya test bir değer döndürür.  
  
##  <a name="unlock"></a>  CComObjectRootEx::Unlock  
 İş parçacığı modeli birden çok iş parçacıklı ise, bu yöntem Win32 API işlevi çağırır [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), kritik bölüm nesnenin hangi sürümleri sahipliğini elde özel veri üyesi.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sahipliği almak için iş parçacığı çağırmalısınız `Lock`. Her çağrı `Lock` karşılık gelen çağrıyı gerektirir `Unlock` kritik bölüm sahipliğini serbest bırakmak için.  
  
 İş parçacığı modeli tek iş parçacıklı ise, bu yöntem hiçbir şey yapmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
