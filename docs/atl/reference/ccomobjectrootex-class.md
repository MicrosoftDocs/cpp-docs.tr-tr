---
title: CComObjectRootEx Sınıfı
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
ms.openlocfilehash: 87e2d7dca81221f4fac2a5189ecb0effbdceddc2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747909"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx Sınıfı

Bu sınıf, hem birleştirilmiş olmayan hem de birleştirilmiş nesneler için nesne başvuru sayısı yönetimini işlemek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Parametreler

*ThreadModel*<br/>
Yöntemleri istenen iş parçacığı modelini uygulayan sınıf. Açıkça [CComSingleThreadModel,](../../atl/reference/ccomsinglethreadmodel-class.md) [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) *threadmodel* ayarlayarak iş parçacığı modeli seçebilirsiniz. *ThreadModel'i* [CComObjectThreadModel veya CComGlobalsThreadModel'e](atl-typedefs.md#ccomobjectthreadmodel) ayarlayarak sunucunun varsayılan iş parçacığı modelini kabul edebilirsiniz. [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ccomobjectrootex](#ccomobjectrootex)|Oluşturucu.|
|[InternalAddref](#internaladdref)|Birbirlemeyen bir nesne için başvuru sayısını artırımı.|
|[Dahili Sürüm](#internalrelease)|Birbirlemeyen bir nesne için başvuru sayısını eriter.|
|[Kilit](#lock)|İş parçacığı modeli çok iş parçacığı varsa, kritik bir bölüm nesnesinin sahipliğini alır.|
|[Kilidini](#unlock)|İş parçacığı modeli çok iş parçacığı varsa, kritik bir bölüm nesnesinin sahipliğini serbest bırakır.|

### <a name="ccomobjectrootbase-methods"></a>CcomObjectRootBase Yöntemleri

|||
|-|-|
|[Finalconstruct](#finalconstruct)|Nesnenizin gerektirdiği herhangi bir başlatmayı gerçekleştirmek için sınıfınızdaki geçersiz kılma.|
|[FinalRelease](#finalrelease)|Nesnenizin gerektirdiği temizlemeyi gerçekleştirmek için sınıfınızdaki geçersiz kılmayı.|
|[DışAddref](#outeraddref)|Toplanan bir nesne için başvuru sayısını artırımı.|
|[DışSorguAra Birimi](#outerqueryinterface)|Toplanan bir nesnenin dış `IUnknown` temsilcisi.|
|[Dış Sürüm](#outerrelease)|Toplanan bir nesne için başvuru sayısını eriter.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|Birbirlemeyen `IUnknown` bir nesnenin temsilcileri.|
|[ObjectMain](#objectmain)|Nesne haritasında listelenen türemiş sınıflar için modül başlatma ve sonlandırma sırasında çağrılır.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[m_dwRef](#m_dwref)|Bir `m_pOuterUnknown`sendikanın parçası yla. Nesne referans sayısını tutmak için toplanmadığında `AddRef` kullanılır `Release`ve .|
|[m_pOuterUnknown](#m_pouterunknown)|Bir `m_dwRef`sendikanın parçası yla. Nesne dış bilinmeyenbir işaretçi tutmak için toplandığında kullanılır.|

## <a name="remarks"></a>Açıklamalar

`CComObjectRootEx`hem birleştirilmiş hem de birleştirilmiş nesneler için nesne başvuru sayımı yönetimini işler. Nesneniz toplanmıyorsa nesne başvuru sayısını tutar ve nesneniz toplanmışsa işaretçiyi dış bilinmeyene tutar. Birleştirilmiş nesneler `CComObjectRootEx` için, iç nesnenin oluşturma daki hatasını işlemek ve iç arabirimler serbest bırakıldığında veya iç nesne silindiğinde dış nesneyi silmeden korumak için yöntemler kullanılabilir.

COM sunucusu uygulayan bir sınıf devralmalı `CComObjectRootEx` veya [CComObjectRoot.](../../atl/reference/ccomobjectroot-class.md)

Sınıf tanımınız [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) makroyu belirtirse, ATL `CComPolyObject<CYourClass>` ne `IClassFactory::CreateInstance` zaman çağrılırken bir örnek oluşturur. Oluşturma sırasında, dış bilinmeyenin değeri denetlenir. NULL ise, `IUnknown` birbirlmeyen bir nesne için uygulanır. Dış bilinmeyen NULL değilse, `IUnknown` birleştirilmiş bir nesne için uygulanır.

Sınıfınız DECLARE_POLY_AGGREGATABLE makrobelirtmezse, ATL birleştirilmiş nesnelerin `CAggComObject<CYourClass>` bir örneğini veya birbirlmeyen nesnelerin örneğini `CComObject<CYourClass>` oluşturur.

Kullanmanın `CComPolyObject` avantajı, birleştirilmiş ve `CComAggObject` `CComObject` birbirlemeyen servis taleplerini işlemek için hem hem de modülünüzde olmasını önlemenizdir. Tek `CComPolyObject` bir nesne her iki durumda da işler. Bu nedenle, modülünüzde vtable'ın yalnızca bir kopyası ve işlevlerin bir kopyası bulunur. Vtable'ınız büyükse, bu durum modül boyutunu önemli ölçüde azaltabilir. Ancak, vtable'ınız küçükse, `CComPolyObject` toplanmış veya birleştirilmiş olmayan bir nesne için optimize `CComAggObject` edilmedikve `CComObject`.

Nesneniz biraraya toplanmışsa, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) tarafından `CComAggObject` veya `CComPolyObject`. Bu sınıflar `QueryInterface` `AddRef`, `Release` , `CComObjectRootEx`ve `OuterQueryInterface`'s çağırır , `OuterAddRef`ve `OuterRelease` dış bilinmeyene iletmek için. Genellikle, toplanan nesneleri `CComObjectRootEx::FinalConstruct` oluşturmak için sınıfınızda geçersiz kılarsınız ve `CComObjectRootEx::FinalRelease` toplanan nesneleri serbest kılmak için geçersiz kılarsınız.

Nesneniz biraraya gelmezse, `IUnknown` ya `CComObject` `CComPolyObject`da . Bu `QueryInterface`durumda, ''''''nin `AddRef` `Release` `CComObjectRootEx` `InternalQueryInterface` `InternalAddRef`, ve gerçek `InternalRelease` işlemleri gerçekleştirmek için ' olarak adverilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>Ccomobjectrootex::ccomobjectrootex

Oluşturucu, başvuru sayısını 0'a göre başlatleştirir.

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>Ccomobjectrootex::finalconstruct

Nesneniz için gerekli olan herhangi bir başlatmayı gerçekleştirmek için türetilmiş sınıfınızda bu yöntemi geçersiz kılabilirsiniz.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı veya standart hata HRESULT değerlerinden biri S_OK döndürün.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalConstruct` yalnızca S_OK döndürür.

Sınıfınızın oluşturucusu `FinalConstruct` yerine başlatma gerçekleştirmenin avantajları vardır:

- Bir kurucudan durum kodu döndüremezsiniz, ancak `FinalConstruct`''nin iade değeri' ile bir HRESULT döndürebilirsiniz. Sınıfınızın nesneleri ATL tarafından sağlanan standart sınıf fabrikası kullanılarak oluşturulurken, bu iade değeri COM istemcisine geri yayılarak ayrıntılı hata bilgileri sağlamanıza olanak sağlar.

- Bir sınıfın oluşturucusundan sanal işlev mekanizması üzerinden sanal işlevleri çağıramazsınız. Bir sınıfın oluşturucusu sanal bir işlev çağrılması, devralma hiyerarşisinde bu noktada tanımlandığı gibi işleviçin statik olarak çözülmüş bir çağrı yla sonuçlanır. Saf sanal işlevlere yapılan çağrılar, bağlayıcı hatalarıyla sonuçlanır.

   Sınıfınız devralma hiyerarşisinde en çok türetilmiş sınıf değildir - bazı işlevlerini sağlamak için ATL tarafından sağlanan türemiş bir sınıfa dayanır. Başlatmanızın bu sınıfın sağladığı özellikleri kullanması gerekebilir (sınıfınızdaki nesnelerin diğer nesneleri toplaması gerektiğinde bu kesinlikle doğrudur), ancak sınıfınızdaki oluşturucunun bu özelliklere erişme şekli yoktur. Sınıfınızın yapı kodu, en çok türetilen sınıf tam olarak oluşturulmadan önce yürütülür.

   Ancak, `FinalConstruct` sanal işlevleri aramanıza ve ATL tarafından sağlanan başvuru sayma uygulamasını kullanmanıza olanak tanıyan en türetilmiş sınıf tam olarak oluşturulduktan hemen sonra çağrılır.

### <a name="example"></a>Örnek

Genellikle, toplanan nesneleri oluşturmak `CComObjectRootEx` için türetilen sınıfta bu yöntemi geçersiz kılmak. Örneğin:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

Yapı başarısız olursa, bir hata döndürebilirsiniz. Makro [DECLARE_PROTECT_FINAL_CONSTRUCT,](aggregation-and-class-factory-macros.md#declare_protect_final_construct) oluşturma sırasında iç toplu nesne başvuru sayısını artımlıve sayıyı 0'a çıkararsa dış nesnenizin silinmesini korumak için de kullanabilirsiniz.

Aşağıda, bir toplu oluşturmanın tipik bir yolu vereme şekli vereme şekli ve

- Sınıf `IUnknown` nesnenize bir işaretçi ekleyin ve oluşturucudaki NULL'a başharf.

- Toplamı `FinalConstruct` oluşturmak için geçersiz kılın.

- COM_INTERFACE_ENTRY_AGGREGATE `IUnknown` makronun parametresi olarak [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) tanımladığınız işaretçiyi kullanın.

- İşaretçiyi `FinalRelease` `IUnknown` serbest bırakmak için geçersiz kılın.

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>Ccomobjectrootex::finalrelease

Nesneniz için gerekli herhangi bir temizleme gerçekleştirmek için türetilmiş sınıfınızda bu yöntemi geçersiz kılabilirsiniz.

```cpp
void FinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalRelease` hiçbir şey yapmaz.

`FinalRelease` Nesne çağrıldığı noktada `FinalRelease` hala tam olarak inşa edildiğinden, temizlemeyi yapmak sınıfınızın yıkıcısına kod eklemekten daha iyidir. Bu, en çok türetilmiş sınıf tarafından sağlanan yöntemlere güvenle erişmenizi sağlar. Bu, özellikle silinmeden önce toplanan nesneleri serbest bırakma için önemlidir.

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>Ccomobjectrootex::internaladdref

Birbirlemeyen bir nesnenin başvuru sayısını 1 ile artışlar.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli çok iş `InterlockedIncrement` parçacığı varsa, aynı anda birden fazla iş parçacığı nın başvuru sayısını değiştirmesini önlemek için kullanılır.

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>CcomObjectRootEx::InternalQueryInterface

İstenen arabirim için bir işaretçi alır.

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*pBu*<br/>
[içinde] Açıkta kalan arabirimlerin COM eşlemi içeren `QueryInterface`nesneye bir işaretçi.

*pEntries*<br/>
[içinde] Kullanılabilir arabirimlerin `_ATL_INTMAP_ENTRY` haritasına erişen yapının işaretçisi.

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*ppvNesne*<br/>
[çıkış] Arabirim bulunamazsa *iid*veya NULL'da belirtilen arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`InternalQueryInterface`yalnızca COM harita tablosundaki arabirimleri işler. Nesneniz biraraya geliyorsa, `InternalQueryInterface` dış bilinmeyene temsilci vermez. Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevlerinden biriyle COM harita tablosuna arayüzler girebilirsiniz.

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>Ccomobjectrootex::Internalrelease

Birbiri toplamı olmayan bir nesnenin başvuru sayısını 1 olarak adlandırın.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Dönüş Değeri

Hem hata ayıklama hem de hata ayıklama oluştururda, bu işlev tanılama veya sınama için yararlı olabilecek bir değer döndürür. Tam döndürülen değer, kullanılan işletim sistemi gibi birçok etkene bağlıdır ve başvuru sayısı olabilir veya olmayabilir.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli çok iş `InterlockedDecrement` parçacığı varsa, aynı anda birden fazla iş parçacığı nın başvuru sayısını değiştirmesini önlemek için kullanılır.

## <a name="ccomobjectrootexlock"></a><a name="lock"></a>CcomObjectRootEx::Kilit

İş parçacığı modeli çok iş parçacığı ise, bu yöntem iş parçacığı özel bir veri üyesi aracılığıyla elde edilen kritik bölüm nesnesinin sahipliğini alabilir kadar bekler Win32 API işlevi [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)çağırır.

```cpp
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Korumalı kod yürütmeyi bitirdiğinde, iş `Unlock` parçacığı kritik bölümün sahipliğini serbest bırakmak için çağrıda gerekir.

İş parçacığı modeli tek iş parçacığı ise, bu yöntem hiçbir şey yapmaz.

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a>CComObjectRootEx::m_dwRef

Dört bayt belleğe erişen bir birliğin parçası.

```
long m_dwRef;
```

### <a name="remarks"></a>Açıklamalar

Bir `m_pOuterUnknown`birliğin parçası ile:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne toplanmış değilse, başvuru sayısı tarafından `AddRef` erişilen ve `m_dwRef` `Release` depolanır. Nesne toplanırsa, dış bilinmeyenişaretçi [m_pOuterUnknown](#m_pouterunknown)depolanır.

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown

Dört bayt belleğe erişen bir birliğin parçası.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Açıklamalar

Bir `m_dwRef`birliğin parçası ile:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne toplanırsa, dış bilinmeyenişaretçi `m_pOuterUnknown`. Nesne toplanmış değilse, başvuru sayısı tarafından `AddRef` erişilen ve `Release` [m_dwRef](#m_dwref)saklanır.

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a>CcomObjectRootEx::ObjectMain

Nesne eşleğinde listelenen her sınıf için, modül baş harfe döndüğünde bu işlev bir kez ve sonlandırıldığında tekrar çağrılır.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Parametreler

*bBaşlangıç*<br/>
[çıkış] Sınıf başharfe çevrilir değeri DOĞRUDUR; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*bBaşlangıç* parametresinin değeri, modülün başlatılıp başlatılmadığını veya sonlandırılıp sonlandırılmadığını gösterir. Varsayılan uygulama `ObjectMain` hiçbir şey yapmaz, ancak sınıf için ayırmak istediğiniz kaynakları başlatmaveya temizlemek için sınıfınızdaki bu işlevi geçersiz kılabilirsiniz. Sınıfın `ObjectMain` herhangi bir örneği istenmeden önce çağrıldığını unutmayın.

`ObjectMain`DLL'nin giriş noktasından çağrılır, bu nedenle giriş noktası işlevinin gerçekleştirebileceği işlem türü kısıtlanır. Bu kısıtlamalar hakkında daha fazla bilgi için [DL'ler ve Visual C++ çalışma zamanı kitaplık davranışı](../../build/run-time-library-behavior.md) ve [DllMain'e](/windows/win32/Dlls/dllmain)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>Ccomobjectrootex::DışAddref

Bir toplamanın dış bilinmeyeninin referans sayısını artırımına eder.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>CcomObjectRootEx::OuterQueryInterface

İstenen arabirime dolaylı bir işaretçi alır.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*ppvNesne*<br/>
[çıkış] Toplama arabirimi desteklemiyorsa, *iid*veya NULL'da belirtilen arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>Ccomobjectrootex::Dış Sürüm

Bir toplamanın dış bilinmeyeninin referans sayısını erteler.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında her zaman 0 döndürür. Hata ayıklama oluştururda, tanılama veya sınama için yararlı olabilecek bir değer verir.

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a>Ccomobjectrootex::Kilidini Aç

İş parçacığı modeli çok iş parçacığı ise, bu yöntem, özel bir veri üyesi aracılığıyla elde edilen kritik bölüm nesnesinin sahipliğini serbest bırakan Win32 API işlevini [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)olarak adlandırır.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Sahipliği elde etmek için `Lock`iş parçacığının araması gerekir. Her çağrı, `Lock` kritik bölümün `Unlock` sahipliğini serbest bırakmak için karşılık gelen bir çağrı gerektirir.

İş parçacığı modeli tek iş parçacığı ise, bu yöntem hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
