---
title: CComObjectRootEx sınıfı
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
ms.openlocfilehash: 8fa4e7a035ded2e1a20dd278a5d54d40252e1958
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417931"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx sınıfı

Bu sınıf, hem toplanmış hem de toplanmış nesneler için nesne başvuru sayısı yönetimini işlemek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Parametreler

*ThreadModel*<br/>
Yöntemleri istenen iş parçacığı modelini uygulayan sınıf. İş parçacığı modelini *ThreadModel* olarak [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)veya [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)olarak ayarlayarak seçebilirsiniz. *ThreadModel* ' i [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)olarak ayarlayarak sunucunun varsayılan iş parçacığı modelini kabul edebilirsiniz.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|Oluşturucu.|
|[InternalAddRef](#internaladdref)|Toplanmayan bir nesne için başvuru sayısını artırır.|
|[InternalRelease](#internalrelease)|Toplanmayan bir nesne için başvuru sayısını azaltır.|
|[İne](#lock)|İş parçacığı modeli çok iş parçacıklı ise, kritik bir bölüm nesnesinin sahipliğini edinir.|
|[Kaldırın](#unlock)|İş parçacığı modeli çok iş parçacıklı ise, kritik bir bölüm nesnesinin sahipliğini yayınlar.|

### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase yöntemleri

|||
|-|-|
|[Sonlandıryapısı](#finalconstruct)|Nesneniz için gereken başlatma işlemini gerçekleştirmek için sınıfınıza geçersiz kılın.|
|[Sonlandırın sürümü](#finalrelease)|Nesneniz için gereken temizleme işlemini gerçekleştirmek için sınıfınıza geçersiz kılın.|
|[OuterAddRef](#outeraddref)|Toplanmış bir nesne için başvuru sayısını artırır.|
|[OuterQueryInterface](#outerqueryinterface)|Toplu bir nesnenin dış `IUnknown` temsilciler.|
|[OuterRelease](#outerrelease)|Toplanmış bir nesne için başvuru sayısını azaltır.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|Toplanmayan bir nesnenin `IUnknown` temsilciler.|
|[ObjectMain](#objectmain)|Modül başlatma sırasında ve nesne eşlemesinde listelenen türetilmiş sınıfların sonlandırılması sırasında çağırılır.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_dwRef](#m_dwref)|`m_pOuterUnknown`, birleşimin bir parçası. Nesne, `AddRef` başvuru sayısını ve `Release`tutmak için toplanmadığınızda kullanılır.|
|[m_pOuterUnknown](#m_pouterunknown)|`m_dwRef`, birleşimin bir parçası. Nesne toplanırsa, bilinmeyen dış öğesine bir işaretçi tutacak şekilde kullanılır.|

## <a name="remarks"></a>Açıklamalar

`CComObjectRootEx` hem toplanmış hem de toplanmış nesneler için nesne başvuru sayısı yönetimini işler. Nesneniz toplanmıyor ise nesne başvuru sayısını tutar ve nesneniz toplanırsa bu, bilinmeyen dış öğesine işaretçiyi barındırır. Toplu nesneler için `CComObjectRootEx` Yöntemler, oluşturulacak iç nesnenin başarısızlığını işlemek ve iç arabirimler serbest bırakıldığında ya da iç nesne silindiğinde, dış nesne silinmeye karşı korumak için kullanılabilir.

COM sunucusu uygulayan bir sınıf `CComObjectRootEx` veya [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)öğesinden kalıtımla almalıdır.

Sınıf tanımınız [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) makrosunu BELIRTIYORSA, ATL `IClassFactory::CreateInstance` çağrıldığında bir `CComPolyObject<CYourClass>` örneği oluşturur. Oluşturma sırasında, bilinmeyen dıştaki değeri denetlenir. NULL ise, toplanmayan bir nesne için `IUnknown` uygulanır. Bilinmeyen dış değer NULL değilse, toplanan bir nesne için `IUnknown` uygulanır.

Sınıfınız DECLARE_POLY_AGGREGATABLE makrosunu belirtmezse, ATL toplanmış nesneler için bir `CAggComObject<CYourClass>` örneği veya toplanmayan nesneler için bir `CComObject<CYourClass>` örneği oluşturur.

`CComPolyObject` kullanmanın avantajı, toplu ve toplu olmayan durumları işlemek için modülünüzün hem `CComAggObject` hem de `CComObject` olmasını önlemenize olanak sağlar. Tek bir `CComPolyObject` nesnesi her iki durumu da işler. Bu nedenle, bir vtable 'ın yalnızca bir kopyası ve işlevlerinizin bir kopyası var. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse `CComPolyObject` kullanmak, `CComAggObject` ve `CComObject`gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden biraz daha büyük bir modül boyutuna neden olabilir.

Nesneniz toplanırsa, [ıunknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) `CComAggObject` veya `CComPolyObject`tarafından uygulanır. Bu sınıflar, bilinmeyen dış öğesine iletmek için `CComObjectRootEx``OuterQueryInterface`, `OuterAddRef`ve `OuterRelease` için `QueryInterface`, `AddRef`ve `Release` çağrılarını devredebilir. Genellikle, derlenmiş nesneleri oluşturmak için sınıfınıza `CComObjectRootEx::FinalConstruct` geçersiz kılar ve toplanmış nesneleri serbest bırakmak için `CComObjectRootEx::FinalRelease` geçersiz kılabilirsiniz.

Nesneniz toplanmadığından, `IUnknown` `CComObject` veya `CComPolyObject`tarafından uygulanır. Bu durumda `QueryInterface`, `AddRef`ve `Release` çağrıları, gerçek işlemleri gerçekleştirmek için `CComObjectRootEx``InternalQueryInterface`, `InternalAddRef`ve `InternalRelease` için atanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="ccomobjectrootex"></a>CComObjectRootEx:: CComObjectRootEx

Oluşturucu başvuru sayısını 0 olarak başlatır.

```
CComObjectRootEx();
```

##  <a name="finalconstruct"></a>CComObjectRootEx:: Finalyapısı

Nesneniz için gereken başlatma işlemini gerçekleştirmek için türetilmiş sınıfınıza bu yöntemi geçersiz kılabilirsiniz.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya standart hata HRESULT değerlerinden birine S_OK döndürün.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalConstruct` S_OK döndürür.

Sınıfınızın Oluşturucusu yerine `FinalConstruct` başlatmayı gerçekleştirmenin avantajları vardır:

- Bir oluşturucudan bir durum kodu döndüremez, ancak `FinalConstruct`dönüş değeri ile bir HRESULT döndürebilirsiniz. Sınıfınızın nesneleri ATL tarafından sunulan standart sınıf fabrikası kullanılarak oluşturulduğunda, bu dönüş değeri COM istemcisine geri dağıtılır ve bunları ayrıntılı hata bilgileri sağlamanıza olanak tanır.

- Bir sınıfın oluşturucusundan sanal işlev mekanizması aracılığıyla sanal işlevleri çağrılamaz. Bir sınıfın oluşturucusundan bir sanal işlevin çağrılması, devralma hiyerarşisinde bu noktada tanımlandığından, işleve statik olarak çözümlenmiş bir çağrıya neden olur. Saf sanal işlevlere yapılan çağrılar bağlayıcı hatalarına neden olacak.

   Sınıfınız devralma hiyerarşisinde en çok türetilen sınıf değildir; bu özellik, bazı işlevlerinden bazılarını sağlamak için ATL tarafından sağlanan türetilmiş bir sınıfa bağımlıdır. Başlatmanın Bu sınıf tarafından sunulan özellikleri kullanması gerektiği konusunda iyi bir fikir vardır (sınıfınızın nesneleri diğer nesneleri toplamanız gerektiğinde bu kesinlikle doğrudur), ancak sınıfınıza olan oluşturucunun bu özelliklere erişme yolu yoktur. Sınıfınız için oluşturma kodu, en çok türetilen sınıf tam olarak oluşturulmadan önce yürütülür.

   Ancak, en çok türetilen sınıf tam olarak oluşturulduktan sonra, sanal işlevleri çağırıp ATL tarafından verilen başvuru sayma uygulamasını kullanmanıza olanak tanıyan `FinalConstruct` hemen çağrılır.

### <a name="example"></a>Örnek

Genellikle, toplanan nesneleri oluşturmak için `CComObjectRootEx` türetilen sınıfta bu yöntemi geçersiz kılın. Örneğin:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

Oluşturma başarısız olursa, bir hata döndürebilir. Ayrıca, oluşturma sırasında iç toplanmış nesne başvuru sayısını artırır ve sonra sayıyı 0 olarak azaltır ve dış nesnenizin silinmesini korumak için makro [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) de kullanabilirsiniz.

Toplama oluşturmanın tipik bir yolu aşağıda verilmiştir:

- Sınıf nesneniz için `IUnknown` bir işaretçi ekleyin ve oluşturucuda NULL olarak başlatın.

- Toplama oluşturmak için `FinalConstruct` geçersiz kılın.

- [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) makrosunda parametre olarak tanımladığınız `IUnknown` işaretçisini kullanın.

- `IUnknown` işaretçisini serbest bırakmak için `FinalRelease` geçersiz kılın.

##  <a name="finalrelease"></a>CComObjectRootEx:: FinalRelease

Nesneniz için gereken herhangi bir temizleme işlemini gerçekleştirmek için, türetilmiş sınıfınıza bu yöntemi geçersiz kılabilirsiniz.

```
void FinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CComObjectRootEx::FinalRelease` hiçbir şey yapmaz.

Nesne hala `FinalRelease` çağrıldığı noktada tamamen oluşturulduğundan, `FinalRelease` Temizleme işleminin yerine, sınıfınızın yıkıcıya kod eklenmesi tercih edilir. Bu, en çok türetilen sınıf tarafından sunulan yöntemlere güvenle erişmenizi sağlar. Bu, silmeden önce toplanmış nesneleri serbest bırakma için özellikle önemlidir.

##  <a name="internaladdref"></a>CComObjectRootEx:: InternalAddRef

Toplanmayan bir nesnenin başvuru sayısını 1 artırır.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli çok iş parçacıklı ise, aynı anda birden fazla iş parçacığının başvuru sayısını değiştirmesini engellemek için `InterlockedIncrement` kullanılır.

##  <a name="internalqueryinterface"></a>CComObjectRootEx:: InternalQueryInterface

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
'ndaki `QueryInterface`sunulan arabirimlerin COM haritasını içeren nesneye yönelik bir işaretçi.

*pEntries*<br/>
'ndaki Kullanılabilir arabirimlerin eşlemesine erişen `_ATL_INTMAP_ENTRY` yapısına yönelik bir işaretçi.

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı Arabirim bulunamazsa, *IID*'de belirtilen arabirim işaretçisi IŞARETÇISI veya null.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`InternalQueryInterface` yalnızca COM Map tablosundaki arabirimleri işler. Nesneniz toplanırsa, `InternalQueryInterface` bilinmeyen dış öğesine temsilci eklemez. COM harita tablosuna, makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevlerinden biri ile arabirimler girebilirsiniz.

##  <a name="internalrelease"></a>CComObjectRootEx:: InternalRelease

Toplanmayan bir nesnenin başvuru sayısını 1 azaltır.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan ve hata ayıklama yapılarında, bu işlev tanılama veya test için yararlı olabilecek bir değer döndürür. Döndürülen tam değer, kullanılan işletim sistemi gibi birçok faktöre bağlıdır ve başvuru sayısı olabilir veya olmayabilir.

### <a name="remarks"></a>Açıklamalar

İş parçacığı modeli çok iş parçacıklı ise, aynı anda birden fazla iş parçacığının başvuru sayısını değiştirmesini engellemek için `InterlockedDecrement` kullanılır.

##  <a name="lock"></a>CComObjectRootEx:: Lock

İş parçacığı modeli çok iş parçacıklı ise, bu yöntem, iş parçacığının özel bir veri üyesi aracılığıyla elde edilen kritik bölüm nesnesinin sahipliğini üstlemeyeceğini bekleyen Win32 API Function [Entercriticalhandle bölümünü](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)çağırır.

```
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Korunan kod yürütmeyi bitirdiğinde, iş parçacığının kritik bölümün sahipliğini serbest bırakmak için `Unlock` çağırması gerekir.

İş parçacığı modeli tek iş parçacıklı ise, bu yöntem hiçbir şey yapmaz.

##  <a name="m_dwref"></a>CComObjectRootEx:: m_dwRef

Dört baytlık belleğe erişen bir birleşimin parçası.

```
long m_dwRef;
```

### <a name="remarks"></a>Açıklamalar

`m_pOuterUnknown`, birleşimin bir parçası:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne toplanmıyorsa, `AddRef` tarafından erişilen başvuru sayısı ve `Release` `m_dwRef`depolanır. Nesne toplanırsa, bilinmeyen dıştaki işaretçi [m_pOuterUnknown](#m_pouterunknown)depolanır.

##  <a name="m_pouterunknown"></a>CComObjectRootEx:: m_pOuterUnknown

Dört baytlık belleğe erişen bir birleşimin parçası.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Açıklamalar

`m_dwRef`, birleşimin bir parçası:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Nesne toplanırsa, bilinmeyen dıştaki işaretçi `m_pOuterUnknown`depolanır. Nesne toplanmıyorsa, `AddRef` tarafından erişilen başvuru sayısı ve `Release` [m_dwRef](#m_dwref)depolanır.

##  <a name="objectmain"></a>CComObjectRootEx:: ObjectMain

Nesne eşlemesinde listelenen her bir sınıf için, bu işlev modül başlatıldığında bir kez ve sonlandırıldığında yeniden çağrılır.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Parametreler

*bStarting*<br/>
dışı Sınıf başlatılmışsa değer TRUE 'dur; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*BStarting* parametresinin değeri, modülün başlatılmış veya sonlandırılmış olduğunu gösterir. `ObjectMain` varsayılan uygulanması hiçbir şey yapmaz, ancak sınıfı için ayırmak istediğiniz kaynakları başlatmak veya temizlemek için sınıfınızdan bu işlevi geçersiz kılabilirsiniz. Sınıfın herhangi bir örneği istenmadan önce `ObjectMain` çağırılır.

`ObjectMain`, DLL 'nin giriş noktasından çağrılır, bu nedenle giriş noktası işlevinin gerçekleştirebileceği işlem türü kısıtlıdır. Bu kısıtlamalar hakkında daha fazla bilgi için bkz. [DLL 'ler C++ ve görsel çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) ve [DllMain](/windows/win32/Dlls/dllmain).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

##  <a name="outeraddref"></a>CComObjectRootEx:: OuterAddRef

Bir toplama için bilinmeyen dış öğenin başvuru sayısını artırır.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

##  <a name="outerqueryinterface"></a>CComObjectRootEx:: OuterQueryInterface

İstenen arabirime dolaylı bir işaretçi alır.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı *IID*'de belirtilen arabirim işaretçisine yönelik bir işaretçi veya toplama ARABIRIMI desteklemiyorsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="outerrelease"></a>CComObjectRootEx:: OuterRelease

Bir toplama için bilinmeyen dış öğenin başvuru sayısını azaltır.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan derlemelerde, her zaman 0 döndürür. Hata ayıklama yapılarında, tanılama veya test için yararlı olabilecek bir değer döndürür.

##  <a name="unlock"></a>CComObjectRootEx:: unlock

İş parçacığı modeli çok iş parçacıklı ise, bu yöntem, özel bir veri üyesi aracılığıyla elde edilen kritik bölüm nesnesinin sahipliğini serbest bırakır [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)Win32 API işlevini çağırır.

```
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Sahipliği almak için iş parçacığının `Lock`çağrısı gerekir. `Lock` yapılan her çağrıya, kritik bölümün sahipliğini serbest bırakmak için `Unlock` için karşılık gelen bir çağrı gerekir.

İş parçacığı modeli tek iş parçacıklı ise, bu yöntem hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
