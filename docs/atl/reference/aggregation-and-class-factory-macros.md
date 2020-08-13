---
title: Toplama ve sınıf fabrikası makroları
ms.date: 08/12/2020
f1_keywords:
- ATLCOM/ATL::DECLARE_AGGREGATABLE
- ATLCOM/ATL::DECLARE_CLASSFACTORY
- ATLCOM/ATL::DECLARE_CLASSFACTORY_EX
- ATLCOM/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLCOM/ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATLCOM/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATLCOM/ATL::DECLARE_NOT_AGGREGATABLE
- ATLCOM/ATL::DECLARE_ONLY_AGGREGATABLE
- ATLCOM/ATL::DECLARE_POLY_AGGREGATABLE
- ATLCOM/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLCOM/ATL::DECLARE_VIEW_STATUS
- ATLDEF/ATL::DECLARE_AGGREGATABLE
- ATLDEF/ATL::DECLARE_CLASSFACTORY
- ATLDEF/ATL::DECLARE_CLASSFACTORY_EX
- ATLDEF/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLDEF/ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATLDEF/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATLDEF/ATL::DECLARE_NOT_AGGREGATABLE
- ATLDEF/ATL::DECLARE_ONLY_AGGREGATABLE
- ATLDEF/ATL::DECLARE_POLY_AGGREGATABLE
- ATLDEF/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLDEF/ATL::DECLARE_VIEW_STATUS
- ATLCOM/DECLARE_AGGREGATABLE
- ATLCOM/DECLARE_CLASSFACTORY
- ATLCOM/DECLARE_CLASSFACTORY_EX
- ATLCOM/DECLARE_CLASSFACTORY_AUTO_THREAD
- ATLCOM/DECLARE_CLASSFACTORY_SINGLETON
- ATLCOM/DECLARE_GET_CONTROLLING_UNKNOWN
- ATLCOM/DECLARE_NOT_AGGREGATABLE
- ATLCOM/DECLARE_ONLY_AGGREGATABLE
- ATLCOM/DECLARE_POLY_AGGREGATABLE
- ATLCOM/DECLARE_PROTECT_FINAL_CONSTRUCT
- ATLCOM/DECLARE_VIEW_STATUS
- ATL::DECLARE_AGGREGATABLE
- ATL::DECLARE_CLASSFACTORY
- ATL::DECLARE_CLASSFACTORY_EX
- ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATL::DECLARE_NOT_AGGREGATABLE
- ATL::DECLARE_ONLY_AGGREGATABLE
- ATL::DECLARE_POLY_AGGREGATABLE
- ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATL::DECLARE_VIEW_STATUS
- DECLARE_AGGREGATABLE
- DECLARE_CLASSFACTORY
- DECLARE_CLASSFACTORY_EX
- DECLARE_CLASSFACTORY_AUTO_THREAD
- DECLARE_CLASSFACTORY_SINGLETON
- DECLARE_GET_CONTROLLING_UNKNOWN
- DECLARE_NOT_AGGREGATABLE
- DECLARE_ONLY_AGGREGATABLE
- DECLARE_POLY_AGGREGATABLE
- DECLARE_PROTECT_FINAL_CONSTRUCT
- DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
- ATL::DECLARE_AGGREGATABLE
- ATL::DECLARE_CLASSFACTORY
- ATL::DECLARE_CLASSFACTORY_EX
- ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- ATL::DECLARE_CLASSFACTORY_SINGLETON
- ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- ATL::DECLARE_NOT_AGGREGATABLE
- ATL::DECLARE_ONLY_AGGREGATABLE
- ATL::DECLARE_POLY_AGGREGATABLE
- ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- ATL::DECLARE_VIEW_STATUS
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 5fdf330cfc69ea68720666eae5952be356cad314
ms.sourcegitcommit: 50db6d0a0d640155c9347c1914bc8859efaadd90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2020
ms.locfileid: "88197336"
---
# <a name="aggregation-and-class-factory-macros"></a>Toplama ve sınıf fabrikası makroları

Bu makrolar, toplamayı ve sınıf fabrikalarını bildirmek için yollar sağlar.

| Makroya | Açıklama |
|--|--|
| [DECLARE_AGGREGATABLE](#declare_aggregatable) | Nesnenizin toplanabilecek olduğunu bildirir (varsayılan). |
| [DECLARE_CLASSFACTORY](#declare_classfactory) | Sınıf fabrikasını [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL varsayılan sınıf fabrikası olacak şekilde bildirir. |
| [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) | Sınıf fabrikası nesnenizin sınıf fabrikası olduğunu bildirir. |
| [DECLARE_CLASSFACTORY2](#declare_classfactory2) | [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıfının sınıf fabrikası olduğunu bildirir. |
| [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) | [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıfını sınıf fabrikası olarak bildirir. |
| [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) | [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) öğesini sınıf fabrikası olarak bildirir. |
| [DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown) | Sanal bir `GetControllingUnknown` işlev bildirir. |
| [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) | Nesnenizin toplanmadığını bildirir. |
| [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) | Nesnenizin toplanması gerektiğini bildirir. |
| [DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable) | Bilinmeyen dış değerin değerini denetler ve uygun şekilde, nesne toplanabilir veya toplanamayan bir şekilde bildirir. |
| [DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct) | İç nesnenin oluşturulması sırasında dış nesnenin silinmesini önler. |
| [DECLARE_VIEW_STATUS](#declare_view_status) | Kapsayıcıya VIEWSTATUS bayraklarını belirtir. |

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a> DECLARE_AGGREGATABLE

Nesnenizin toplanabilecek olduğunu belirtir.

```cpp
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanabilir olarak tanımladığınız sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan toplama modelini belirtmek için bu makroyu içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızda [declare_not_aggregatable](#declare_not_aggregatable) ya da [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) makrosunu belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a> DECLARE_CLASSFACTORY

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi sınıf fabrikası olarak bildirir.

```cpp
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesneniz için varsayılan sınıf fabrikasını bildirmek üzere bu makroyu kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a> CComClassFactory sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular.

```cpp
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactory` belirli bir CLSID 'nin bir nesnesi oluşturmak için gereken ve yeni nesnelerin daha hızlı oluşturulmasına izin vermek için bellekte sınıf fabrikasını kilitleyen [ıssfactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular. `IClassFactory` , sistem kayıt defterine kaydettiğinizde ve bir CLSID atadığınız her sınıf için uygulanmalıdır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [DECLARE_CLASSFACTORY](#declare_classfactory) `CComClassFactory` varsayılan sınıf fabrikası olarak bildiren DECLARE_CLASSFACTORY makro içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızda DECLARE_CLASSFACTORY*XXX* makrolarından birini belirtin. Örneğin, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) makro sınıf fabrikası için belirtilen sınıfı kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Yukarıdaki sınıf tanımı `CMyClassFactory` , nesnenin varsayılan sınıf fabrikası olarak kullanılacağını belirtir. `CMyClassFactory` türevi `CComClassFactory` ve override olmalıdır `CreateInstance` .

ATL, bir sınıf fabrikası bildiren üç farklı makro sağlar:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) , Bir lisans aracılığıyla oluşturmayı denetleyen [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)kullanır.

- [declare_classfactory_auto_thread](#declare_classfactory_auto_thread) Birden çok apartmanlarda nesneler oluşturan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)kullanır.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Tek bir [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi oluşturan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)kullanır.

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a> DECLARE_CLASSFACTORY_EX

`cf`Sınıf fabrikası olduğunu bildirir.

```cpp
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
'ndaki Sınıf fabrikası nesneniz uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

*CF* parametresi [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilmelidir ve yöntemi geçersiz kılmalıdır `CreateInstance` .

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [DECLARE_CLASSFACTORY](#declare_classfactory) `CComClassFactory` varsayılan sınıf fabrikası olarak belirten DECLARE_CLASSFACTORY makrosunu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_EX makrosunu ekleyerek bu varsayılanı geçersiz kılabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a> DECLARE_CLASSFACTORY2

[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) sınıfının sınıf fabrikası olduğunu bildirir.

```cpp
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Parametreler

*lik*<br/>
'ndaki , Ve uygulayan bir `VerifyLicenseKey` sınıf `GetLicenseKey` `IsLicenseValid` .

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY2 makrosunu ekleyerek bu varsayılanı geçersiz kılabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a> CComClassFactory2 sınıfı

Bu sınıf [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular.

```cpp
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

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)'nin bir uzantısı olan [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular. `IClassFactory2` bir lisans aracılığıyla nesne oluşturmayı denetler. Lisanslı bir makinede yürütülen bir sınıf fabrikası, çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı, bir tam makine lisansı mevcut olmadığında bir uygulamanın nesneleri örneketmesine olanak tanır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](#declare_classfactory)makro içerir. Kullanmak için `CComClassFactory2` , nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY2](#declare_classfactory2) makrosunu belirtin. Örnek:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, için şablon parametresi, `CComClassFactory2` ve statik işlevlerini uygulamalıdır `VerifyLicenseKey` `GetLicenseKey` `IsLicenseValid` . Aşağıda basit bir lisans sınıfına bir örnek verilmiştir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` hem hem de `CComClassFactory2Base` *lisandan*türetilir. `CComClassFactory2Base`sırasıyla, `IClassFactory2` ve **CComObjectRootEx \< CComGlobalsThreadModel > **öğesinden türetilir.

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a> DECLARE_CLASSFACTORY_AUTO_THREAD

[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıfını sınıf fabrikası olarak bildirir.

```cpp
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_AUTO_THREAD makrosunu ekleyerek bu varsayılanı geçersiz kılabilirsiniz.

Birden çok apartmanlarda (işlem dışı bir sunucuda) nesne oluşturduğunuzda, sınıfınıza DECLARE_CLASSFACTORY_AUTO_THREAD ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a> CComClassFactoryAutoThread sınıfı

Bu sınıf, [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve nesnelerin birden çok apartmanlarda oluşturulmasına izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```cpp
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread` , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ile benzerdir, ancak nesnelerin birden çok apartmanlarda oluşturulmasına izin verir. Bu destekten faydalanmak için, [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)' dan exe modülünüzü türetebilirsiniz.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](#declare_classfactory)makro içerir. Kullanmak için `CComClassFactoryAutoThread` , nesnenizin sınıf tanımında [declare_classfactory_auto_thread](#declare_classfactory_auto_thread) makrosunu belirtin. Örnek:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a> DECLARE_CLASSFACTORY_SINGLETON

[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) öğesini sınıf fabrikası olarak bildirir.

```cpp
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
'ndaki Sınıf nesnenizin adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makrosunu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_SINGLETON makrosunu ekleyerek bu varsayılanı geçersiz kılabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a> CComClassFactorySingleton sınıfı

Bu sınıf [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```cpp
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız.

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır. Yöntemine yapılan her çağrı `CreateInstance` yalnızca bir arabirim işaretçisi için bu nesneyi sorgular.

### <a name="remarks"></a>Açıklamalar

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [DECLARE_CLASSFACTORY](#declare_classfactory) `CComClassFactory` varsayılan sınıf fabrikası olarak bildiren DECLARE_CLASSFACTORY makro içerir. Kullanmak için `CComClassFactorySingleton` , nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) makrosunu belirtin. Örnek:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a> DECLARE_GET_CONTROLLING_UNKNOWN

Sanal bir işlev bildirir `GetControllingUnknown` .

```cpp
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Açıklamalar

Tanımsız bir derleyici hata iletisi alırsanız, bu makroyu nesneniz `GetControllingUnknown` içine ekleyin (örneğin, içinde `CComAggregateCreator` ).

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a> DECLARE_NOT_AGGREGATABLE

Nesnenizin toplanmadığını belirtir.

```cpp
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanamayan olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

DECLARE_NOT_AGGREGATABLE `CreateInstance` , nesnenizin toplamaya yönelik bir girişim yapılırsa bir hata (CLASS_E_NOAGGREGATION) döndürmesine neden olur.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesnenizin toplanabilecek olduğunu belirten [declare_aggregatable](#declare_aggregatable) makrosunu içerir. Bu varsayılan davranışı geçersiz kılmak için DECLARE_NOT_AGGREGATABLE sınıf tanımınıza dahil edin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a> DECLARE_ONLY_AGGREGATABLE

Nesnenizin toplanması gerektiğini belirtir.

```cpp
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Yalnızca toplanabilir olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

DECLARE_ONLY_AGGREGATABLE, `CoCreate` nesnenizin toplanmayan nesne olarak bir girişim yapılırsa bir hataya neden olur (E_FAIL).

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) , nesnenizin toplanabilecek olduğunu belirten [declare_aggregatable](#declare_aggregatable) makrosunu içerir. Bu varsayılan davranışı geçersiz kılmak için DECLARE_ONLY_AGGREGATABLE sınıf tanımınıza dahil edin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a> DECLARE_POLY_AGGREGATABLE

Nesneniz oluşturulduğunda **CComPolyObject \<** *x* **> ** örneğinin oluşturulacağını belirtir.

```cpp
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Toplanamayan veya toplanamayan sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

Oluşturma sırasında, bilinmeyen dıştaki değeri denetlenir. NULL ise, `IUnknown` toplanmayan bir nesne için uygulanır. Bilinmeyen dış değer NULL değilse, `IUnknown` toplanmış bir nesne için uygulanır.

DECLARE_POLY_AGGREGATABLE kullanmanın avantajı, `CComAggObject` `CComObject` toplu ve toplu olmayan durumları işlemek için modülünüzün her ikisine de sahip olmasını önlemenize olanak sağlar. Tek bir `CComPolyObject` nesne her iki durumu da işler. Bu, bir vtable 'ın yalnızca bir kopyasının ve modülünüzün bir kopyasının mevcut olduğu anlamına gelir. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse,, `CComPolyObject` ve gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden, kullanmak biraz daha büyük bir modül boyutuna neden olabilir `CComAggObject` `CComObject` .

Tam denetim oluşturmak için ATL Denetim Sihirbazı 'nı kullanırsanız, DECLARE_POLY_AGGREGATABLE makrosu nesneniz içinde otomatik olarak belirtilir.

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a> DECLARE_PROTECT_FINAL_CONSTRUCT

( [Finalyapı](ccomobjectrootex-class.md#finalconstruct)sırasında), iç toplanmış nesne başvuru sayısını artırırsa, bu, sayıyı 0 olarak azaltır.

```cpp
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a> DECLARE_VIEW_STATUS

Bu makroyu, kapsayıcıya VIEWSTATUS bayraklarını belirtmek için bir ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```cpp
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Parametreler

*statusFlags*<br/>
'ndaki VIEWSTATUS bayrakları. Bayrakların listesi için bkz. [Viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
