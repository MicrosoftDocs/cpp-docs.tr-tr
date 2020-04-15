---
title: Toplama ve Sınıf Üreticisi Makroları
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
ms.openlocfilehash: 33f33043d1a2c824ada26399365541796178d21d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319333"
---
# <a name="aggregation-and-class-factory-macros"></a>Toplama ve Sınıf Üreticisi Makroları

Bu makrolar, toplamayı denetlemenin ve sınıf fabrikalarını bildirmenin yollarını sağlar.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Nesnenizin toklayalabileceğini bildirir (varsayılan).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Sınıf fabrikasını [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL varsayılan sınıf fabrikası olarak bildirir.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Sınıf fabrika nesnenizi sınıf fabrikası olarak bildirir.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|[CComClassFactory2'yi](../../atl/reference/ccomclassfactory2-class.md) sınıf fabrikası olarak bildirir.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|[CComClassFactoryAutoThread'i](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf fabrikası olarak bildirir.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|[CComClassFactorySingleton'ı](../../atl/reference/ccomclassfactorysingleton-class.md) sınıf fabrikası olarak bildirir.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Sanal `GetControllingUnknown` bir işlev bildirir.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Nesnenizin toklanamaz olduğunu bildirir.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Nesnenizin biraraya edilmesi gerektiğini bildirir.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Dış bilinmeyenin değerini denetler ve nesnenizi toplanıp toplanıp toplanmaz, uygun olarak bildirir.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Bir iç nesnenin yapımı sırasında dış nesneyi silmeye karşı korur.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Kapsayıcıya VIEWSTATUS bayraklarını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

Nesnenizin toklanınabileceğini belirtir.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Toplayıcı olarak tanımladığınız sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan toplama modelini belirtmek için bu makroyu içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızda [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) veya [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) makroyu belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

[CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass](../../atl/reference/ccomcoclass-class.md) nesneniz için varsayılan sınıf fabrika bildirmek için bu makrokullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>CcomclassFactory Sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactory`belirli bir CLSID nesnesi oluşturmak için yöntemler içeren [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve yeni nesnelerin daha hızlı oluşturulmasına izin vermek için sınıf fabrikasını bellekte kilitler. `IClassFactory`sistem kayıt defterine kaydettiğiniz ve clsid atadığınız her sınıf için uygulanmalıdır.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [DECLARE_CLASSFACTORY](#declare_classfactory)varsayılan sınıf fabrikası `CComClassFactory` olarak bildiren makro DECLARE_CLASSFACTORY içerir. Bu varsayılanı geçersiz kılmak için, sınıf tanımınızdaki DECLARE_CLASSFACTORY*XXX* makrolarından birini belirtin. Örneğin, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) makro sınıf fabrikası için belirtilen sınıfı kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Yukarıdaki sınıf tanımı, nesnenin varsayılan sınıf fabrikası olarak kullanılacak belirtir. `CMyClassFactory` `CMyClassFactory`türetin `CComClassFactory` ve geçersiz `CreateInstance`kılmalıdır.

ATL, sınıf fabrikası nı bildiren diğer üç makro sağlar:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) Bir lisans aracılığıyla oluşturma yı kontrol eden [CComClassFactory2'yi](../../atl/reference/ccomclassfactory2-class.md)kullanır.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Birden çok dairenesneleri oluşturur [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)kullanır.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Tek bir [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi oluşturan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)kullanır.

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

Sınıf `cf` fabrikası olduğunu beyan eder.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
[içinde] Sınıf fabrika nesnenizi uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

*Cf* parametresi [CComClassFactory'den](../../atl/reference/ccomclassfactory-class.md) türemelidir `CreateInstance` ve yöntemi geçersiz kılar.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan [DECLARE_CLASSFACTORY](#declare_classfactory) sınıf fabrika olarak `CComClassFactory` belirtir DECLARE_CLASSFACTORY makro içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_EX makroyu ekleyerek bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

[CComClassFactory2'yi](../../atl/reference/ccomclassfactory2-class.md) sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Parametreler

*Lisansı*<br/>
[içinde] Bir sınıf uygular `VerifyLicenseKey` `GetLicenseKey`, `IsLicenseValid`, ve .

### <a name="remarks"></a>Açıklamalar

[CComCoClass,](../../atl/reference/ccomcoclass-class.md) [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makroyu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY2 makroyu ekleyerek bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>CcomclassFactory2 Sınıfı

Bu sınıf [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Parametreler

*Lisans*<br/>
Aşağıdaki statik işlevleri uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Açıklamalar

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)bir uzantısıdır [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arayüzü, uygular. `IClassFactory2`bir lisans aracılığıyla nesne oluşturmayı denetler. Lisanslı bir makinede çalışan bir sınıf fabrikası, çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı, tam makine lisansı olmadığında bir uygulamanın nesneleri anında ani olarak anlamasına olanak tanır.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak bildiren makro [DECLARE_CLASSFACTORY](#declare_classfactory)içerir. Kullanmak `CComClassFactory2`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY2](#declare_classfactory2) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, şablon `CComClassFactory2`parametresi için , `VerifyLicenseKey`statik `GetLicenseKey`işlevleri `IsLicenseValid`uygulamak gerekir , ve . Aşağıdaki basit bir lisans sınıfı örneğidir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`hem de `CComClassFactory2Base` *lisans*türetilmiştir. `CComClassFactory2Base`, sırayla, ve `IClassFactory2` **CComObjectRootEx\< CComGlobalsThreadModel >** türetilmiştir.

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

[CComClassFactoryAutoThread'i](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Açıklamalar

[CComCoClass,](../../atl/reference/ccomcoclass-class.md) [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makroyu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_AUTO_THREAD makroyu ekleyerek bu varsayılanı geçersiz kılarsınız.

Birden çok dairede (proc dışı bir sunucuda) nesneler oluşturduğunuzda, sınıfınıza DECLARE_CLASSFACTORY_AUTO_THREAD ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>CcomclassFactoryAutoThread Sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve nesnelerin birden çok dairede oluşturulmasına izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)benzer, ancak nesnelerin birden çok daire de oluşturulmasını sağlar. Bu destekten yararlanmak için EXE modülünüzü [CComAutoThreadModule'den](../../atl/reference/ccomautothreadmodule-class.md)türetin.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak bildiren makro [DECLARE_CLASSFACTORY](#declare_classfactory)içerir. Kullanmak `CComClassFactoryAutoThread`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

[CComClassFactorySingleton'ı](../../atl/reference/ccomclassfactorysingleton-class.md) sınıf fabrikası olarak bildirir.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
[içinde] Sınıf nesnenizin adı.

### <a name="remarks"></a>Açıklamalar

[CComCoClass,](../../atl/reference/ccomcoclass-class.md) [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak belirten [DECLARE_CLASSFACTORY](#declare_classfactory) makroyu içerir. Ancak, nesnenizin sınıf tanımına DECLARE_CLASSFACTORY_SINGLETON makroyu ekleyerek bu varsayılanı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton Sınıfı

Bu sınıf [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) türetilmiştir ve tek bir nesne oluşturmak için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Senin sınıfın.

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) türetilmiştir ve tek bir nesne oluşturmak için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır. Yönteme `CreateInstance` yapılan her çağrı, bu nesneyi bir arabirim işaretçisi için sorgular.

### <a name="remarks"></a>Açıklamalar

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [DECLARE_CLASSFACTORY](#declare_classfactory)varsayılan sınıf fabrikası `CComClassFactory` olarak bildiren makro DECLARE_CLASSFACTORY içerir. Kullanmak `CComClassFactorySingleton`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

Sanal bir işlev `GetControllingUnknown`bildirir.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Açıklamalar

Tanımlanmamış derleyici hata iletisi `GetControllingUnknown` alırsanız (örneğin, içinde) `CComAggregateCreator`bu makroyu nesnenize ekleyin.

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

Nesnenizin toklanamaz olduğunu belirtir.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Tanımladığınız sınıf nesnesinin adı toplanamaz.

### <a name="remarks"></a>Açıklamalar

DECLARE_NOT_AGGREGATABLE `CreateInstance` nesnenize bir toplama girişiminde bulunulması durumunda hata (CLASS_E_NOAGGREGATION) döndürülmeye neden olur.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) nesnenizin toplanabilir belirten [DECLARE_AGGREGATABLE](#declare_aggregatable) makro içerir. Bu varsayılan davranışı geçersiz kılmak için sınıf tanımına DECLARE_NOT_AGGREGATABLE ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

Nesnenizin biraraya edilmesi gerektiğini belirtir.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Yalnızca toplayıcı olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

DECLARE_ONLY_AGGREGATABLE, `CoCreate` nesnenize bir toplamasız nesne olarak bir girişimyapılırsa bir hataya (E_FAIL) neden olur.

Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) nesnenizin toplanabilir belirten [DECLARE_AGGREGATABLE](#declare_aggregatable) makro içerir. Bu varsayılan davranışı geçersiz kılmak için sınıf tanımınızda DECLARE_ONLY_AGGREGATABLE ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

Nesneniz oluşturulduğunda **CComPolyObject \< ** *x* **>** örneğinin oluşturulduğunu belirtir.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Ayırılabilir veya toplanamaz olarak tanımladığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

Oluşturma sırasında, dış bilinmeyenin değeri denetlenir. NULL ise, `IUnknown` birbirlmeyen bir nesne için uygulanır. Dış bilinmeyen NULL değilse, `IUnknown` birleştirilmiş bir nesne için uygulanır.

DECLARE_POLY_AGGREGATABLE kullanmanın avantajı, birleştirilmiş `CComAggObject` ve `CComObject` toplamsız vakaları işlemek için hem modülünüzün hem de modülünüzde olmasını önlemenizdir. Tek `CComPolyObject` bir nesne her iki durumda da işler. Bu, modülünüzde vtable'ın yalnızca bir kopyası ve işlevlerin bir kopyası olduğu anlamına gelir. Vtable'ınız büyükse, bu durum modül boyutunu önemli ölçüde azaltabilir. Ancak, vtable'ınız küçükse, `CComPolyObject` toplanmış veya birleştirilmiş olmayan bir nesne için optimize `CComAggObject` edilmedikve `CComObject`.

Tam denetim oluşturmak için ATL Denetim Sihirbazı'nı kullanırsanız, DECLARE_POLY_AGGREGATABLE makrosu nesnenizde otomatik olarak bildirilir.

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

[(FinalConstruct](ccomobjectrootex-class.md#finalconstruct)sırasında) iç toplu nesne başvuru sayısını artımlıve sonra da sayıyı 0'a çıkarırsa nesnenizi silinmekten korur.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS

Kapsayıcıya VIEWSTATUS bayraklarını belirtmek için bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Parametreler

*durumBayraklar*<br/>
[içinde] VIEWSTATUS bayrakları. Bayrak listesi için [VIEWSTATUS'a](/windows/win32/api/ocidl/ne-ocidl-viewstatus) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
