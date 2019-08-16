---
title: Toplama ve sınıf fabrikası makroları
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
ms.openlocfilehash: 38239942b99a29b5777deef8000d9f1ab85b10e6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492195"
---
# <a name="aggregation-and-class-factory-macros"></a>Toplama ve sınıf fabrikası makroları

Bu makrolar, toplamayı ve sınıf fabrikalarını bildirmek için yollar sağlar.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Nesnenizin toplanabilecek olduğunu bildirir (varsayılan).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Sınıf fabrikasını [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL varsayılan sınıf fabrikası olacak şekilde bildirir.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Sınıf fabrikası nesnenizin sınıf fabrikası olduğunu bildirir.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıfının sınıf fabrikası olduğunu bildirir.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıfını sınıf fabrikası olarak bildirir.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) öğesini sınıf fabrikası olarak bildirir.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Sanal `GetControllingUnknown` bir işlev bildirir.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Nesnenizin toplanmadığını bildirir.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Nesnenizin toplanması gerektiğini bildirir.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Bilinmeyen dış değerin değerini denetler ve uygun şekilde, nesne toplanabilir veya toplanamayan bir şekilde bildirir.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|İç nesnenin oluşturulması sırasında dış nesnenin silinmesini önler.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Kapsayıcıya VIEWSTATUS bayraklarını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

Nesnenizin toplanabilecek olduğunu belirtir.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanabilir olarak tanımladığınız sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan toplama modelini belirtmek için bu makroyu içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızda [declare_not_aggregatable](#declare_not_aggregatable) veya [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) makrosunu belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesneniz için varsayılan sınıf fabrikasını bildirmek üzere bu makroyu kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>CComClassFactory sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactory`belirli bir CLSID 'nin bir nesnesi oluşturmak için gereken ve yeni nesnelerin daha hızlı oluşturulmasına izin vermek için bellekte sınıf fabrikasını kilitleyen [ıssfactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular. `IClassFactory`, sistem kayıt defterine kaydettiğinizde ve bir CLSID atadığınız her sınıf için uygulanmalıdır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, varsayılan sınıf [](#declare_classfactory)fabrikası olarak bildiren `CComClassFactory` DECLARE_CLASSFACTORY makrosunu içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızda DECLARE_CLASSFACTORY*XXX* makrolarından birini belirtin. Örneğin, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) makrosu sınıf fabrikası için belirtilen sınıfı kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Yukarıdaki sınıf tanımı, nesnenin varsayılan `CMyClassFactory` sınıf fabrikası olarak kullanılacağını belirtir. `CMyClassFactory`türevi `CComClassFactory` ve override `CreateInstance`olmalıdır.

ATL, bir sınıf fabrikası bildiren üç farklı makro sağlar:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) , Bir lisans aracılığıyla oluşturmayı denetleyen [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)kullanır.

- [declare_classfactory_auto_thread](#declare_classfactory_auto_thread) Birden çok apartmanlarda nesneler oluşturan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)kullanır.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Tek bir [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi oluşturan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)kullanır.

##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

Sınıf `cf` fabrikası olduğunu bildirir.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
'ndaki Sınıf fabrikası nesneniz uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

*CF* parametresi [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilmelidir `CreateInstance` ve yöntemi geçersiz kılmalıdır.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , varsayılan [](#declare_classfactory) sınıf fabrikası olarak belirten `CComClassFactory` DECLARE_CLASSFACTORY makrosunu içerir. Ancak, DECLARE_CLASSFACTORY_EX makrosunu nesnenizin sınıf tanımına dahil ederek, bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıfının sınıf fabrikası olduğunu bildirir.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Parametreler

*lik*<br/>
'ndaki , `VerifyLicenseKey` `GetLicenseKey`Ve uygulayanbirsınıf.`IsLicenseValid`

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, DECLARE_CLASSFACTORY2 makrosunu nesnenizin sınıf tanımına dahil ederek, bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>CComClassFactory2 sınıfı

Bu sınıf [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Parametreler

*lisan*<br/>
Aşağıdaki statik işlevleri uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Açıklamalar

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)'nin bir uzantısı olan [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular. `IClassFactory2`bir lisans aracılığıyla nesne oluşturmayı denetler. Lisanslı bir makinede yürütülen bir sınıf fabrikası, çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı, bir tam makine lisansı mevcut olmadığında bir uygulamanın nesneleri örneketmesine olanak tanır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](#declare_classfactory)makrosunu içerir. Kullanmak `CComClassFactory2`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY2](#declare_classfactory2) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, için `CComClassFactory2`şablon parametresi, ve `GetLicenseKey` `IsLicenseValid`statik işlevlerini `VerifyLicenseKey`uygulamalıdır. Aşağıda basit bir lisans sınıfına bir örnek verilmiştir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`hem hem de `CComClassFactory2Base` *lisandan*türetilir. `CComClassFactory2Base`sırasıyla, `IClassFactory2` ve **\< CComObjectRootEx CComGlobalsThreadModel >** türetilir.

##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıfını sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, DECLARE_CLASSFACTORY_AUTO_THREAD makrosunu nesnenizin sınıf tanımına dahil ederek, bu varsayılanı geçersiz kılarsınız.

Birden çok apartmanlarda (işlem dışı bir sunucuda) nesne oluştururken, sınıfınıza DECLARE_CLASSFACTORY_AUTO_THREAD ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread sınıfı

Bu sınıf, [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve nesnelerin birden çok apartmanlarda oluşturulmasına izin verir.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread`, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ile benzerdir, ancak nesnelerin birden çok apartmanlarda oluşturulmasına izin verir. Bu destekten faydalanmak için, [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)' dan exe modülünüzü türetebilirsiniz.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](#declare_classfactory)makrosunu içerir. Kullanmak `CComClassFactoryAutoThread`için, nesnenizin sınıf tanımında [declare_classfactory_auto_thread](#declare_classfactory_auto_thread) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) öğesini sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
'ndaki Sınıf nesnenizin adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, DECLARE_CLASSFACTORY_SINGLETON makrosunu nesnenizin sınıf tanımına dahil ederek, bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton sınıfı

Bu sınıf [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız.

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır. `CreateInstance` Yöntemine yapılan her çağrı yalnızca bir arabirim işaretçisi için bu nesneyi sorgular.

### <a name="remarks"></a>Açıklamalar

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, varsayılan sınıf [](#declare_classfactory)fabrikası olarak bildiren `CComClassFactory` DECLARE_CLASSFACTORY makrosunu içerir. Kullanmak `CComClassFactorySingleton`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

Sanal bir işlev `GetControllingUnknown`bildirir.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Açıklamalar

Tanımsız bir `GetControllingUnknown` derleyici hata iletisi alırsanız, bu makroyu nesneniz içine ekleyin (örneğin, içinde `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

Nesnenizin toplanmadığını belirtir.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanamayan olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

Declare_not_aggregatable, `CreateInstance` nesneniz üzerinde toplama için bir girişim yapılırsa bir hata (CLASS_E_NOAGGREGATION) döndürmesine neden olur.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesnenizin toplanabilecek olduğunu belirten [declare_aggregatable](#declare_aggregatable) makrosunu içerir. Bu varsayılan davranışı geçersiz kılmak için, sınıf tanımınıza DECLARE_NOT_AGGREGATABLE ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

Nesnenizin toplanması gerektiğini belirtir.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Yalnızca toplanabilir olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

DECLARE_ONLY_AGGREGATABLE, Eğer nesneniz için `CoCreate` toplanmayan nesne olarak bir girişim yapılırsa bir hataya neden olur (E_FAIL).

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesnenizin toplanabilecek olduğunu belirten [declare_aggregatable](#declare_aggregatable) makrosunu içerir. Bu varsayılan davranışı geçersiz kılmak için, sınıf tanımınıza DECLARE_ONLY_AGGREGATABLE ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

Nesneniz oluşturulduğunda  **\< CComPolyObject** *x* **>** örneğinin oluşturulacağını belirtir.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanamayan veya toplanamayan sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

Oluşturma sırasında, bilinmeyen dıştaki değeri denetlenir. NULL ise, `IUnknown` toplanmayan bir nesne için uygulanır. Bilinmeyen dış değer null değilse, `IUnknown` toplanmış bir nesne için uygulanır.

DECLARE_POLY_AGGREGATABLE kullanmanın avantajı, toplu ve toplu olmayan durumları işlemek için `CComAggObject` modülünüzün her ikisine `CComObject` de sahip olmasını önlemenize olanak sağlar. Tek `CComPolyObject` bir nesne her iki durumu da işler. Bu, bir vtable 'ın yalnızca bir kopyasının ve modülünüzün bir kopyasının mevcut olduğu anlamına gelir. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse,, `CComPolyObject` `CComAggObject` ve `CComObject`gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden, kullanmak biraz daha büyük bir modül boyutuna neden olabilir.

DECLARE_POLY_AGGREGATABLE makrosu, tam denetim oluşturmak için ATL Denetim Sihirbazı 'nı kullanırsanız nesneniz içinde otomatik olarak tanımlanır.

##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

( [Finalyapı](ccomobjectrootex-class.md#finalconstruct)sırasında), iç toplanmış nesne başvuru sayısını artırırsa, bu, sayıyı 0 olarak azaltır.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS

Bu makroyu, kapsayıcıya VIEWSTATUS bayraklarını belirtmek için bir ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Parametreler

*statusFlags*<br/>
'ndaki VIEWSTATUS bayrakları. Bayrakların listesi için bkz. [Viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)
