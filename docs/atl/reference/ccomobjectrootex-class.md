---
title: CComObjectRootEx Class
ms.date: 11/04/2016
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
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: 06a0c0e4b650945e10015c3220b926399ec9c6fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246319"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx Class

Bu sınıf, toplanmayan ve toplanan nesneler için nesne başvuru sayısı Yönetimi işlemek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Parametreler

*ThreadModel*<br/>
İstenen iş parçacığı modeli yöntemleri uygulayan sınıf. İş parçacığı modeli ayarlayarak açıkça seçebilirsiniz *ThreadModel* için [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), veya [ CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Sunucunun varsayılan iş parçacığı modeli ayarlayarak kabul edebilir *ThreadModel* için [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|Oluşturucu.|
|[Internaladdref](#internaladdref)|Toplanmayan bir nesne için başvuru sayısını artırır.|
|[Internalrelease](#internalrelease)|Toplanmayan bir nesne için başvuru sayısını azaltır.|
|[Kilit](#lock)|İş parçacığı modeli birden çok iş parçacığı, kritik bölüm nesnenin sahipliğini alır.|
|[Kilit açma](#unlock)|İş parçacığı modeli birden çok iş parçacığı, kritik bölüm nesnenin sahipliğini serbest bırakır.|

### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase yöntemleri

|||
|-|-|
|[FinalConstruct](#finalconstruct)|Sınıfınızda, bir nesne tarafından gereken herhangi bir başlatma gerçekleştirmek için geçersiz kılın.|
|[FinalRelease](#finalrelease)|Sınıfınızda, nesneye gerekli tüm temizleme işlemlerini gerçekleştirmek için geçersiz kılın.|
|[OuterAddRef](#outeraddref)|Toplanan nesne için başvuru sayısını artırır.|
|[OuterQueryInterface](#outerqueryinterface)|Temsilciler için dış `IUnknown` toplu bir nesne.|
|[OuterRelease](#outerrelease)|Toplanan nesne için başvuru sayısını azaltır.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|Devreder `IUnknown` toplanmayan bir nesne.|
|[ObjectMain](#objectmain)|Modül başlatma ve sonlandırma nesne eşlemesindeki listelenen türetilmiş sınıflar için sırasında çağrılan.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_dwRef](#m_dwref)|İle `m_pOuterUnknown`, bir birleşimin parçası. Nesne başvuru sayımını tutacak toplanmaz çağrılırken `AddRef` ve `Release`.|
|[m_pOuterUnknown](#m_pouterunknown)|İle `m_dwRef`, bir birleşimin parçası. Nesne için dış bilinmeyen bir işaretçi tutacak toplanır olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

`CComObjectRootEx` toplanmayan ve toplanan nesneler için nesne başvuru sayısı management işler. Nesnenizin değil toplanmakta olan ve nesnenizin toplanır, için dış bilinmeyen işaretçi tutan nesne başvuru sayısını tutar. Toplanan nesneler için `CComObjectRootEx` yöntemleri, iç nesneyi oluşturmak için hatasını işlemek için kullanılabilir ve iç nesne dış nesne iç arabirimleri yayımlandığında silinmeye karşı koru için silinir.

Bir COM sunucusu uygulayan bir sınıf devralmalıdır `CComObjectRootEx` veya [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).

Sınıf tanımına belirtiyorsa [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) makrosu, ATL bir örneğini oluşturur `CComPolyObject<CYourClass>` olduğunda `IClassFactory::CreateInstance` çağrılır. Oluşturma sırasında dış bilinmeyen değerini denetlenir. NULL ise `IUnknown` toplanmayan bir nesne için uygulanır. Dış bilinmeyen NULL değilse `IUnknown` toplanan nesne için uygulanır.

Sınıfınıza DECLARE_POLY_AGGREGATABLE makrosu belirtmezse, ATL örneği oluşturur. `CAggComObject<CYourClass>` toplanan nesneler veya bir örneği için `CComObject<CYourClass>` toplanmayan nesneler için.

Kullanmanın avantajı `CComPolyObject` ikisinin önlemek olan `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesi, her iki durumda işler. Bu nedenle, yalnızca bir kopyasını vtable ve işlevlerin bir kopya, modülünüzde mevcut. Vtable büyükse, bu, modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesnesi için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.

Nesne toplanırsa, [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) tarafından uygulanan `CComAggObject` veya `CComPolyObject`. Bu sınıfların temsilci `QueryInterface`, `AddRef`, ve `Release` çağrılar `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, ve `OuterRelease` için dış bilinmeyen iletmek için. Genellikle, geçersiz kılmanız `CComObjectRootEx::FinalConstruct` sınıfınızda, toplanan tüm nesneleri oluşturmak ve yok saymak için `CComObjectRootEx::FinalRelease` herhangi boşaltmak için nesneleri toplanır.

Nesnenizin toplanmaz, `IUnknown` tarafından uygulanan `CComObject` veya `CComPolyObject`. Bu durumda, çağrılar `QueryInterface`, `AddRef`, ve `Release` için temsilci `CComObjectRootEx`'s `InternalQueryInterface`, `InternalAddRef`, ve `InternalRelease` gerçek işlemleri gerçekleştirmek için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx

Oluşturucu, 0 başvuru sayımı başlatır.

```
CComObjectRootEx();
```

##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct

Nesneniz için gereken tüm başlatma gerçekleştirmek için türetilmiş sınıfta bu yöntemin üzerine yazabilir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK HRESULT değerlerini başarı veya standart hata birini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalConstruct` yalnızca S_OK döndürür.

Başlangıçta gerçekleştirme avantajları vardır `FinalConstruct` sınıfınızın Oluşturucusu yerine:

- Oluşturucudan durum kodu iade edemezsiniz, ancak bir HRESULT yoluyla döndürebilir `FinalConstruct`ın dönüş değeri. ATL tarafından sağlanan standart sınıf üretecini kullanarak, sınıfın nesneleri oluşturulan, bu dönüş değeri ile ayrıntılı hata bilgileri vermenizi sağlayan COM istemcisi yayılır.

- Sanal işlevler, bir sınıfın oluşturucudan sanal işlev mekanizması aracılığıyla çağrılamıyor. Bu noktada devralma hiyerarşisinde tanımlandığı gibi statik olarak çözümlenen bir işleve çağrı, bir sınıfın oluşturucusunda bir sanal işlev çağırma sonuçlanır. Saf sanal işlevler için çağrıları bağlayıcı hatalara neden.

   Sınıfınıza en çok türetilen sınıf devralma hiyerarşisinde değil; bazı işlevlerini sağlamak için ATL tarafından sağlanan bir türetilmiş sınıf kullanır. Başlatma işleminiz bu sınıfı (diğer nesneler, sınıfın nesneleri gerekir bu kesinlikle geçerlidir) tarafından sağlanan özellikleri kullanmak için gereken şansı yoktur ancak kendi sınıfınızı oluşturucuda özelliklere erişim için bir yolu yoktur. En çok türetilen sınıf tam oluşturulmamış önce sınıfınız için yapı kod yürütülür.

   Ancak, `FinalConstruct` hemen sonra en çok türetilen sınıf tam olarak sanal işlevleri çağırma ve ATL tarafından sağlanan başvuru sayımı uygulamasını etmenize imkan sağlar oluşturulur çağrılır

### <a name="example"></a>Örnek

Genellikle, türetilen sınıfta bu yöntemin `CComObjectRootEx` herhangi oluşturmak için nesneleri toplanır. Örneğin:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

Yapı başarısız olursa, bir hata döndürebilir. Makro kullanabilirsiniz [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) dış nesnenizin olması korumak için oluşturma sırasında toplanan iç nesne başvuru sayısını sonra azaltır 0 sayısını artırır, silindi.

Bir toplama oluşturmak için normal bir şekilde şöyledir:

- Ekleme bir `IUnknown` sınıfınıza işaretçi nesnesinin ve oluşturucuda NULL olarak başlatın.

- Geçersiz kılma `FinalConstruct` toplama oluşturmak için.

- Kullanım `IUnknown` işaretçi parametresi olarak tanımlanan [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) makrosu.

- Geçersiz kılma `FinalRelease` yayımlamayı `IUnknown` işaretçi.

##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease

Nesneniz için gereken tüm temizleme işlemlerini gerçekleştirmek için türetilmiş sınıfta bu yöntemin üzerine yazabilir.

```
void FinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalRelease` hiçbir şey yapmaz.

Temizleme gerçekleştiriliyor `FinalRelease` nesne kesiştiği noktada hala tam olarak oluşturulmuş olduğundan sınıfınızın yıkıcı için kod eklemeye tercih edilir `FinalRelease` çağrılır. Bu en çok türetilen sınıfı tarafından sağlanan yöntemleri güvenli bir şekilde erişmenize olanak sağlar. Bu özellikle silmeden önce toplanan tüm nesneleri serbest bırakma için önemlidir.

##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef

Toplanmayan bir nesnenin başvuru sayısının 1 artar.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı ve test olabilir bir değer.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli birden çok iş parçacıklı, ise `InterlockedIncrement` birden fazla iş parçacığı aynı anda başvuru sayısı değiştirmesini engellemek için kullanılır.

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

*pThis*<br/>
[in] Açık arabirimler COM haritasını içeren nesneye bir işaretçi `QueryInterface`.

*pEntries*<br/>
[in] Bir işaretçi `_ATL_INTMAP_ENTRY` kullanılabilir arabirim haritasını erişen yapısı.

*IID*<br/>
[in] İstenen arabiriminin GUID'si.

*ppvObject*<br/>
[out] Belirtilen arabirim işaretçisini bir işaretçi *IID*, veya arabirim bulunamazsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`InternalQueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler. Nesne toplanırsa, `InternalQueryInterface` için dış bilinmeyen temsilci değil. COM eşlemesi tablosuna makro arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.

##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease

Başvuru sayısını azaltır toplanmayan bir nesne tarafından 1.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Dönüş Değeri

İçinde hem de hata ayıklama olmayan ve hata ayıklama derlemeleri, bu işlev, tanılama için kullanışlı veya test olabilen bir değer döndürür. Kullanıldığında, işletim sistemi gibi birçok faktöre bağlıdır ve olabilir veya olabilir değil tam değeri döndürdü, başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli birden çok iş parçacıklı, ise `InterlockedDecrement` birden fazla iş parçacığı aynı anda başvuru sayısı değiştirmesini engellemek için kullanılır.

##  <a name="lock"></a>  CComObjectRootEx::Lock

İş parçacığı modeli birden çok iş parçacıklı ise, Win32 API işlevi bu yöntemi çağırır [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection), alınan bir özel veri üyesi iş parçacığı, kritik bölüm nesne sahipliğini kadar hangi bekler.

```
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Korumalı kod yürütme sona erdiğinde, iş parçacığı çağırmalıdır `Unlock` kritik bölüm sahipliğini serbest bırakmak için.

Bu yöntem, iş parçacığı modeli tek iş parçacıklı ise, hiçbir şey yapmaz.

##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef

Dört bayt bellek erişen bir birleşimin parçası.

```
long m_dwRef;
```

### <a name="remarks"></a>Açıklamalar

İle `m_pOuterUnknown`, birleşimin bir bölüm:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne değil toplanırsa, başvuru sayısı erişilen `AddRef` ve `Release` depolanan `m_dwRef`. Nesne toplanırsa, dış bilinmeyen işaretçi depolanan [m_pOuterUnknown](#m_pouterunknown).

##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown

Dört bayt bellek erişen bir birleşimin parçası.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Açıklamalar

İle `m_dwRef`, birleşimin bir bölüm:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne toplanırsa, dış bilinmeyen işaretçi depolanan `m_pOuterUnknown`. Nesne değil toplanırsa, başvuru sayısı erişilen `AddRef` ve `Release` depolanan [m_dwRef](#m_dwref).

##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain

Modül, başlatıldıktan sonra nesne eşlemesindeki listelenen her bir sınıf için bu işlev çağrılır ve yeniden zaman bunu sonlandırılır.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Parametreler

*bStarting*<br/>
[out] Değer TRUE ise sınıfı başlatılır. Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Değerini *bStarting* parametresi gösterir modülü yüklenmekte olan başlatıldı veya sonlandırıldı. Varsayılan uygulaması `ObjectMain` hiçbir şey yapmaz, ancak bu işlev başlatmak veya sınıf için ayırmak istediğiniz kaynakları temizlemek için sınıfınızda geçersiz kılabilirsiniz. Unutmayın `ObjectMain` sınıfın tüm örnekleri istenen önce çağrılır.

`ObjectMain` kısıtlı giriş noktası işlevi gerçekleştirebilir işlem türü, bu nedenle, DLL giriş noktasından çağrılır. Bu kısıtlamalar hakkında daha fazla bilgi için bkz. [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) ve [DllMain](/windows/desktop/Dlls/dllmain).

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

İstenen arabirim için dolaylı bir işaretçi alır.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] İstenen arabiriminin GUID'si.

*ppvObject*<br/>
[out] Belirtilen arabirim işaretçisini bir işaretçi *IID*, veya toplama arabirimini desteklemiyor yoksa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease

Dış bilinmeyen bir toplama başvuru sayısını azaltır.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan yapılarında, her zaman 0 değerini döndürür. Hata ayıklama yapılarında, tanılama için kullanışlı veya test olabilecek bir değer döndürür.

##  <a name="unlock"></a>  CComObjectRootEx::Unlock

İş parçacığı modeli birden çok iş parçacıklı ise, Win32 API işlevi bu yöntemi çağırır [LeaveCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection), kritik bölüm nesnenin hangi sürümler sahipliğini elde bir özel veri üyesi.

```
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı sahipliğini almayı çağırmalıdır `Lock`. Her çağrı `Lock` karşılık gelen bir çağrı gerektirir `Unlock` kritik bölüm sahipliğini serbest bırakmak için.

Bu yöntem, iş parçacığı modeli tek iş parçacıklı ise, hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
