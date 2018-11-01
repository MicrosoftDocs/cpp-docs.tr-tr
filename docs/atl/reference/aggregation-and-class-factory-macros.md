---
title: Toplama ve sınıf üreticisi makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: c0e3b6903e382ad56be9500792bec895a7641f00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497200"
---
# <a name="aggregation-and-class-factory-macros"></a>Toplama ve sınıf üreticisi makroları

Bu makrolar, toplama denetleme ve sınıf üreteçlerini bildirme yollar sağlar.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Nesneniz olduğunu bildirir (varsayılan) toplanır.|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Sınıf üreteci olarak bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL varsayılan sınıf üreteci.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Sınıf üreteci olacak şekilde, sınıf üretecini bildirir.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Bildirir [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıf üreteci olacak.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Bildirir [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf üreteci olacak.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Bildirir [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) sınıf üreteci olacak.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Bir sanal bildirir `GetControllingUnknown` işlevi.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Nesnenizin toplanamaz bildirir.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Nesnenizin toplanmalıdır bildirir.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Dış bilinmeyen değerini denetler ve toplanabilir veya toplanabilir değil, uygun şekilde, nesne bildirir.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Dış nesne iç bir nesnenin yapımı sırasında silmeye karşı korur.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Kapsayıcıya VIEWSTATUS bayrakları belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE

Nesnenizin toplanabilir belirtir.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Toplanabilir olarak tanımlıyorsanız sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan toplama modelini belirtmek için bu makroyu içerir. Bu varsayılanı geçersiz kılmak için seçeneklerinden birini belirtin [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) veya [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) sınıfı Tanımınızda makrosu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY

Bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) sınıf üreteci olacak.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) nesneniz için varsayılan sınıf üreteci bildirmek için bu makroyu kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>  CComClassFactory sınıfı

Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimi.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactory` uygulayan [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimi, yeni nesneler daha hızlı bir şekilde oluşturulmasına izin vermek için bellekte sınıf üreteci kilitleme yanı sıra belirli bir CLSID bir nesne oluşturmak için yöntemleri içerir. `IClassFactory` Sistem kayıt defterinde ve CLSID atamak için kaydettiğiniz her sınıf için uygulanmalıdır.

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir `CComClassFactory` olarak varsayılan sınıf üreteci. Bu varsayılanı geçersiz kılmak için DECLARE_CLASSFACTORY birini belirtin*XXX* sınıf tanımına makrolarındaki. Örneğin, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) makrosu belirtilen sınıfı için sınıf üreteci kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Yukarıdaki sınıf tanımı belirten `CMyClassFactory` nesnenin varsayılan sınıf üreteci kullanılır. `CMyClassFactory` öğesinden türetilmelidir `CComClassFactory` ve geçersiz kılma `CreateInstance`.

ATL bir sınıf üreteci bildirmek üç makroları sağlar:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) kullanan [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), bir lisans ile oluşturma denetler.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) kullanan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), içinde birden çok apartmanlar nesneleri oluşturur.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) kullanan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), tek bir yapıları [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesne.

##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX

Bildirir `cf` sınıf üreteci olacak.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Parametreler

*cf*<br/>
[in] Sınıf üretecini uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

*Cf* parametresi türetilmesi gereken [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve geçersiz kılma `CreateInstance` yöntemi.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) içerir [DECLARE_CLASSFACTORY](#declare_classfactory) belirten makrosu `CComClassFactory` olarak varsayılan sınıf üreteci. Ancak, DECLARE_CLASSFACTORY_EX makrosu, nesnenin sınıf tanımında dahil ederek, bu varsayılanı geçersiz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2

Bildirir [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıf üreteci olacak.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Parametreler

*Lisans Sözleşmesi*<br/>
[in] Uygulayan bir sınıf `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) içerir [DECLARE_CLASSFACTORY](#declare_classfactory) belirten makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Ancak, DECLARE_CLASSFACTORY2 makrosu, nesnenin sınıf tanımında dahil ederek, bu varsayılanı geçersiz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>  CComClassFactory2 sınıfı

Bu sınıfın uyguladığı [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) arabirimi.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Parametreler

*Lisans*<br/>
Aşağıdaki statik işlevler uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Açıklamalar

`CComClassFactory2` uygulayan [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) uzantısıdır arabirimi, [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` bir lisans ile denetimleri nesne oluşturma. Bir sınıf üreteci lisanslı bir makinede çalıştırma, bir çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı tam makine lisans yoksa nesneleri somutlaştırmak bir uygulama sağlar.

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactory2`, belirtin [DECLARE_CLASSFACTORY2](#declare_classfactory2) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, şablon parametresi olarak `CComClassFactory2`, statik işlevler uygulamalıdır `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`. Aşağıdaki basit lisans sınıfının bir örneğidir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` hem türetilen `CComClassFactory2Base` ve *lisans*. `CComClassFactory2Base`, sırasıyla türetildiği `IClassFactory2` ve **CComObjectRootEx\< CComGlobalsThreadModel >**.

##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD

Bildirir [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf üreteci olacak.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) içerir [DECLARE_CLASSFACTORY](#declare_classfactory) belirten makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Ancak, DECLARE_CLASSFACTORY_AUTO_THREAD makrosu, nesnenin sınıf tanımında dahil ederek, bu varsayılanı geçersiz.

(İşlem dışı Server'daki) birden çok apartmanlar nesneler oluşturduğunuzda DECLARE_CLASSFACTORY_AUTO_THREAD sınıfınıza ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>  CComClassFactoryAutoThread sınıfı

Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirim ve nesnelerin içinde birden çok apartmanlar oluşturulmasına izin verir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread` benzer [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ancak nesnelerin içinde birden çok apartmanlar oluşturulmasına izin verir. Bu destek avantajlarından yararlanmak için EXE modülünden türetilen [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactoryAutoThread`, belirtin [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON

Bildirir [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) sınıf üreteci olacak.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
[in] Sınıfı nesne adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) içerir [DECLARE_CLASSFACTORY](#declare_classfactory) belirten makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Ancak, DECLARE_CLASSFACTORY_SINGLETON makrosu, nesnenin sınıf tanımında dahil ederek, bu varsayılanı geçersiz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>  CComClassFactorySingleton sınıfı

Bu sınıfın türetildiği [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturmak için.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza.

`CComClassFactorySingleton` öğesinden türetilen [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturmak için. Her çağrı `CreateInstance` yöntemi yalnızca bu nesne bir arabirim işaretçisi için sorgular.

### <a name="remarks"></a>Açıklamalar

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir `CComClassFactory` olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactorySingleton`, belirtin [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN

Sanal bir işlev bildirir `GetControllingUnknown`.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Açıklamalar

Derleyici hata iletisi alırsanız bu makro, nesnesine ekleme `GetControllingUnknown` tanımlı değil (örneğin, `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE

Nesnenizin toplanamaz belirtir.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Sınıfı nesne adı olarak toplanabilir tanımlıyorsunuz.

### <a name="remarks"></a>Açıklamalar

DECLARE_NOT_AGGREGATABLE neden `CreateInstance` denemesi yapılırsa (CLASS_E_NOAGGREGATION) bir hata döndürmek için nesnenin üzerine toplanacak.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_AGGREGATABLE](#declare_aggregatable) nesnenizin toplanabilir belirten makrosu. Bu varsayılan davranışı geçersiz kılmak için sınıf tanımında DECLARE_NOT_AGGREGATABLE içerir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>  DECLARE_ONLY_AGGREGATABLE

Nesnenizin toplanması gereken belirtir.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Yalnızca toplanabilir tanımladığınız sınıf nesnesi adı.

### <a name="remarks"></a>Açıklamalar

DECLARE_ONLY_AGGREGATABLE neden bir hata (E_FAIL) denemesi yapılırsa `CoCreate` nesnenizin toplanmayan bir nesne.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_AGGREGATABLE](#declare_aggregatable) nesnenizin toplanabilir belirten makrosu. Bu varsayılan davranışı geçersiz kılmak için sınıf tanımında DECLARE_ONLY_AGGREGATABLE içerir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE

Belirten bir örneğini **CComPolyObject \<**  *x* **>** nesnenizin oluşturduğunuzda oluşturulur.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Toplanabilir veya toplanabilir değil olarak tanımlayan sınıf nesnesi adı.

### <a name="remarks"></a>Açıklamalar

Oluşturma sırasında dış bilinmeyen değerini denetlenir. NULL ise `IUnknown` toplanmayan bir nesne için uygulanır. Dış bilinmeyen NULL değilse `IUnknown` toplanan nesne için uygulanır.

İkisinin önlemek DECLARE_POLY_AGGREGATABLE kullanmanın avantajı olduğu `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesi, her iki durumda işler. Bu işlevler bir kopyasını ve yalnızca bir kopyasını vtable modülünüzde mevcut anlamına gelir. Vtable büyükse, bu, modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesnesi için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.

Tam bir denetim oluşturmak için ATL Denetim Sihirbazı'nı kullanırsanız DECLARE_POLY_AGGREGATABLE makrosu, nesne otomatik olarak bildirilir.

##  <a name="declare_protect_final_construct"></a>  DECLARE_PROTECT_FINAL_CONSTRUCT

Nesneniz varsa silinmiş korur (sırasında [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) iç toplanan nesne başvuru sayısını sonra azaltır 0 sayısını artırır.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS

Bir ATL ActiveX denetiminin denetim sınıfı kapsayıcıya VIEWSTATUS bayrakları belirtmek için bu makroyu yerleştirin.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Parametreler

*statusFlags*<br/>
[in] VIEWSTATUS bayraklar. Bkz: [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) bayrakların listesi için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
