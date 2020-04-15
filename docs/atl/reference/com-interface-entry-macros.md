---
title: COM Arabirimi Giriş Makroları
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: bb7498f639f463290a4a6593ef7c0fbac09b539b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326686"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY Makrolar

Bu makrolar, bir nesnenin arabirimlerine COM haritasına girer, `QueryInterface`böylece bunlara . COM haritasındaki girişlerin sırası, sipariş arabirimlerinin sırasında `QueryInterface`eşleşen bir IID için kontrol edilmesidir.

|||
|-|-|
|[Com_ınterface_entry](#com_interface_entry)|Arayüzleri COM arabirim haritasına girer.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Bu makroyu, iki kalıtım dalını ayrıştırmak için kullanın.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Arabirimi COM haritasına girmek ve IID'sini belirtmek için bu makroyu kullanın.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|[COM_INTERFACE_ENTRY2](#com_interface_entry2)ile aynı , ancak farklı bir IID belirtebilirsiniz.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|*iid* tarafından tanımlanan arabirim için `COM_INTERFACE_ENTRY_AGGREGATE` sorgulandığında, `punk`'' için iletme|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), herhangi bir IID sonuçları için sorgu *punk*sorgulanması dışında .|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)aynı , *punk* NULL dışında, otomatik olarak *clsid*tarafından açıklanan toplam oluşturur.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), punk sorgu yönlendirme herhangi bir IID sonuçları dışında *,* ve *punk* NULL ise, otomatik olarak *clsid*tarafından açıklanan toplam oluşturma .|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Belirtilen arabirim sorgulandığında programınızın [Hata Sonu'nu](/windows/win32/api/debugapi/nf-debugapi-debugbreak) aramasına neden olur.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Her örnek için arabirime özgü verileri kaydeder.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Yırtılma arayüzlerinizi ortaya çıkarır.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|İşlem, COM haritasında bu girişe ulaştığında taban sınıfın COM haritasını işler.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL'nin mantığına kanca takmak için genel bir `QueryInterface` mekanizma.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)aynı , *func*bir çağrı herhangi bir IID sonuçları için sorgulama dışında .|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Belirtilen arabirim sorgulandığında E_NOINTERFACE döndürür ve COM eşlem işlemeyi sonlandırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a>Com_ınterface_entry

Arayüzleri COM arabirim haritasına girer.

### <a name="syntax"></a>Sözdizimi

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Sınıf nesnenizin doğrudan türetilmiştir bir arabirim adı.

### <a name="remarks"></a>Açıklamalar

Genellikle, bu en sık kullandığınız giriş türüdür.

### <a name="example"></a>Örnek

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2

Bu makroyu, iki kalıtım dalını ayrıştırmak için kullanın.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Nesnenizden açığa çıkarmak istediğiniz bir arabirimin adı.

*x2*<br/>
[içinde] *x'in* maruz kaldığı kalıtım dalının adı.

### <a name="remarks"></a>Açıklamalar

Örneğin, sınıf nesnenizi iki çift arabirimden türetederseniz, `IDispatch` arabirimlerden herhangi birinden elde edilebildiği için COM_INTERFACE_ENTRY2 kullanarak ortaya çıkarabilirsiniz. `IDispatch`

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID

Arabirimi COM haritasına girmek ve IID'sini belirtmek için bu makroyu kullanın.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Açık arabirimin GUID'i.

*X*<br/>
[içinde] Vtable *iid*tarafından tanımlanan arabirim olarak ortaya çıkacak sınıfın adı .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID

[COM_INTERFACE_ENTRY2](#com_interface_entry2)ile aynı , ancak farklı bir IID belirtebilirsiniz.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Arabirim için belirttiğiniz GUID.

*X*<br/>
[içinde] Sınıf nesnenizin doğrudan türetdiği bir arabirimin adı.

*x2*<br/>
[içinde] Sınıf nesnenizin doğrudan türetdiği ikinci bir arabirimin adı.

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE

*iid* tarafından tanımlanan arayüz için sorgulandığında, COM_INTERFACE_ENTRY_AGGREGATE *ileri ye doğru punk.*

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Arabirimin GUID'i için sorgulandı.

*Punk*<br/>
[içinde] Bir `IUnknown` işaretçinin adı.

### <a name="remarks"></a>Açıklamalar

*Punk* parametresi, bir agreganın iç bilinmeyenine veya NULL'a işaret ettiği varsayılır ve bu durumda giriş yoksayılır. Genellikle, toplam `CoCreate` `FinalConstruct`olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND

Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), herhangi bir IID sonuçları için sorgu *punk*sorgulanması dışında .

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Bir `IUnknown` işaretçinin adı.

### <a name="remarks"></a>Açıklamalar

Arabirim sorgusu başarısız olursa, COM eşleminin işlenmesi devam eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)aynı , *punk* NULL dışında, otomatik olarak *clsid*tarafından açıklanan toplam oluşturur.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Arabirimin GUID'i için sorgulandı.

*Punk*<br/>
[içinde] Bir `IUnknown` işaretçinin adı. COM eşlesini içeren sınıfın bir üyesi olmalıdır.

*Clsıd*<br/>
[içinde] *Punk* NULL ise oluşturulacak toplam Tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), punk sorgu yönlendirme herhangi bir IID sonuçları dışında *,* ve *punk* NULL ise, otomatik olarak *clsid*tarafından açıklanan toplam oluşturma .

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Bir `IUnknown` işaretçinin adı. COM eşlesini içeren sınıfın bir üyesi olmalıdır.

*Clsıd*<br/>
[içinde] *Punk* NULL ise oluşturulacak toplam Tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Arabirim sorgusu başarısız olursa, COM eşleminin işlenmesi devam eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK

Belirtilen arabirim sorgulandığında programınızın [Hata Sonu'nu](/windows/win32/api/debugapi/nf-debugapi-debugbreak) aramasına neden olur.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Arabirim tanımlayıcısını oluşturmak için kullanılan metin.

### <a name="remarks"></a>Açıklamalar

IID arabirimi *x'e* `IID_`eklenerek oluşturulacaktır. Örneğin, *x* ise, `IPersistStorage`IID olacaktır. `IID_IPersistStorage`

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Her örnek için arabirime özgü verileri kaydeder.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Yırtılma arabiriminin GUID'i.

*X*<br/>
[içinde] Arabirimi uygulayan sınıfın adı.

*Punk*<br/>
[içinde] Bir `IUnknown` işaretçinin adı. COM eşlesini içeren sınıfın bir üyesi olmalıdır. Sınıf nesnesinin oluşturucusunda NULL'a başharflenmelidir.

### <a name="remarks"></a>Açıklamalar

Arabirim kullanılmazsa, bu nesnenizin genel örnek boyutunu düşürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF

Yırtılma arayüzlerinizi ortaya çıkarır.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Yırtılma arabiriminin GUID'i.

*X*<br/>
[içinde] Arabirimi uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Yırtılma arabirimi, temsil ettiği arabirim için her sorgulandığında anlık olarak ayrı bir nesne olarak uygulanır. Genellikle, arabirim nadiren kullanıldığından, ana nesnenizin her örneğinde bir vtable işaretçisi kaydettiğinden, arabiriminizi yırtılma olarak oluşturursunuz. Başvuru sayısı sıfır olduğunda yırtılma silinir. Yırtılma yıkıntısını uygulayan `CComTearOffObjectBase` sınıf, kendi COM haritasından türetilmeli ve kendi COM haritasına sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN

İşlem, COM haritasında bu girişe ulaştığında taban sınıfın COM haritasını işler.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
[içinde] Geçerli nesnenin taban sınıfı.

### <a name="remarks"></a>Açıklamalar

Örneğin, aşağıdaki kodda:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM haritasındaki ilk girişin, COM eşlemi içeren nesneüzerinde bir arabirim olması gerektiğini unutmayın. Bu nedenle, farklı bir nesnenin COM haritasının nesnenizin COM haritasında **COM_INTERFACE_ENTRY_CHAIN**`COtherObject`**görünmesine** neden olan COM_INTERFACE_ENTRY_CHAIN ile COM eşlemi girişlerinizi başlatamazsınız. Önce başka bir nesnenin COM haritasında arama yapmak `IUnknown` istiyorsanız, COM haritanıza bir arayüz girişi ekleyin ve ardından diğer nesnenin COM haritasını zincirle. Örneğin:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC

ATL'nin mantığına kanca takmak için genel bir `QueryInterface` mekanizma.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Açık arabirimin GUID'i.

*Dw*<br/>
[içinde] Func'ye geçen *func*bir parametre.

*func*<br/>
[içinde] iid döndürecek işlev *işaretçisi*.

### <a name="remarks"></a>Açıklamalar

*iid,* sorgulanmış arabirimin IID'si ile eşleşiyorsa, *func* tarafından belirtilen işlev çağrılır. İşlev için bildirim olmalıdır:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

Işleviniz çağrıldığında, `pv` sınıf nesnenizi işaret eder. *Riid* parametresi için sorgulanan arabirim `ppv` anlamına gelir, işlevin arabiriminişaretçisini depolaması gereken konuma işaretçive *dw* girişte belirttiğiniz parametredir. İşlev NULL \* `ppv` olarak ayarlanmalı ve arabirim döndürmemeyi seçerse E_NOINTERFACE veya S_FALSE döndürmelidir. E_NOINTERFACE ile, COM eşleme işleme sona erer. S_FALSE ile, hiçbir arabirim işaretçisi döndürülmemesine rağmen COM eşleme işleme devam eder. İşlev bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND

[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)aynı , *func*bir çağrı herhangi bir IID sonuçları için sorgulama dışında .

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Parametreler

*Dw*<br/>
[içinde] Func'ye geçen *func*bir parametre.

*func*<br/>
[içinde] COM eşlemindeki bu giriş işlendiğinde çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Herhangi bir hata, işlemin COM haritasında devam etmesine neden olur. İşlev bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE

Belirtilen arabirim sorgulandığında E_NOINTERFACE döndürür ve COM eşlem işlemeyi sonlandırır.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Arabirim tanımlayıcısını oluşturmak için kullanılan metin.

### <a name="remarks"></a>Açıklamalar

Bu makroyu, belirli bir durumda bir arabirimin kullanılmasını önlemek için kullanabilirsiniz. Örneğin, arabirimin sorgusunun toplamın iç bilinmeyenine iletilmesine engel olmak için bu makroyu COM_INTERFACE_ENTRY_AGGREGATE_BLIND önce COM haritanıza ekleyebilirsiniz.

IID arabirimi *x'e* `IID_`eklenerek oluşturulacaktır. Örneğin, *x* ise, `IPersistStorage`IID olacaktır. `IID_IPersistStorage`
