---
description: 'Hakkında daha fazla bilgi edinin: COM_INTERFACE_ENTRY makrolar'
title: COM arabirimi giriş makroları
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
ms.openlocfilehash: 0564c1e4ba6b9778865442d281453ff3a4a56d7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141368"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY makrolar

Bu makrolar, tarafından erişilebilmesi için COM eşlemesine bir nesnenin arabirimlerini girer `QueryInterface` . COM eşlemesindeki girdilerin sırası, sırasında eşleşen bir IID için sıralama arayüzlerinin denetlenecektir `QueryInterface` .

|Makroya|Açıklama|
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Arabirimleri COM arabirim eşlemesine girer.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Bu makroyu, devralma için iki dalı ortadan kaldırmak için kullanın.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Arabirimi COM haritasına girmek ve IID 'sini belirtmek için bu makroyu kullanın.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|[COM_INTERFACE_ENTRY2](#com_interface_entry2)ile aynı, farklı bir IID belirtebileceğiniz sürece.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|*IID* tarafından tanımlanan arabirim için sorgulandığında, ' a `COM_INTERFACE_ENTRY_AGGREGATE` iletir `punk` .|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)ile aynı, hiçbir IID sorgusunun sorgu *punk*'a iletilmesinin sonucu olduğu durumlar dışında.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)ile aynı, *punk* null olması dışında, *CLSID* tarafından tanımlanan toplamı otomatik olarak oluşturur.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|COM_INTERFACE_ENTRY_AUTOAGGREGATE ile aynı, hiçbir IID sorgusunun sorgu *punk*'a iletime ve *punk* null olması dışında, *CLSID* tarafından tanımlanan toplamı otomatik olarak oluşturan [](#com_interface_entry_autoaggregate).|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Belirtilen arabirim için sorgulandığında programınızın [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) ' i çağırmasını sağlar.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Her örnek için arabirime özgü verileri kaydeder.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Yırma arabirimlerini gösterir.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|İşlem COM eşlemesinde bu girişe ulaştığında taban sınıfının COM haritasını işler.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL 'nin mantığını aramak için genel bir mekanizma `QueryInterface` .|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)ile aynıdır, ancak HERHANGI bir IID sorgusu *Func* çağrısı ile sonuçlanır.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|E_NOINTERFACE döndürür ve belirtilen arabirim için sorgulandığında COM eşleme işlemesini sonlandırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

Arabirimleri COM arabirim eşlemesine girer.

### <a name="syntax"></a>Sözdizimi

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Sınıf nesnenizin doğrudan türediği arabirimin adı.

### <a name="remarks"></a>Açıklamalar

Genellikle bu, en sık kullandığınız giriş türüdür.

### <a name="example"></a>Örnek

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a> COM_INTERFACE_ENTRY2

Bu makroyu, devralma için iki dalı ortadan kaldırmak için kullanın.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Nesnenizin sergilemek istediğiniz arabirimin adı.

*x2*<br/>
'ndaki *X* 'in açığa çıkarılan devralma dalının adı.

### <a name="remarks"></a>Açıklamalar

Örneğin, iki çift arabirimden sınıf nesneniz türetirsiniz, `IDispatch` `IDispatch` arabirimlerinden birinden elde edilmesinden bu yana COM_INTERFACE_ENTRY2 kullanarak kullanıma sunabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a> COM_INTERFACE_ENTRY_IID

Arabirimi COM haritasına girmek ve IID 'sini belirtmek için bu makroyu kullanın.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Sunulan arabirimin GUID 'SI.

*x*<br/>
'ndaki Vtable, *IID* tarafından tanımlanan arabirim olarak kullanıma sunulacak olan sınıfın adı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a> COM_INTERFACE_ENTRY2_IID

[COM_INTERFACE_ENTRY2](#com_interface_entry2)ile aynı, farklı bir IID belirtebileceğiniz sürece.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Arabirim için belirttiğiniz GUID.

*x*<br/>
'ndaki Sınıf nesnenizin doğrudan türediği arabirimin adı.

*x2*<br/>
'ndaki Sınıf nesnenizin doğrudan türediği ikinci arabirimin adı.

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a> COM_INTERFACE_ENTRY_AGGREGATE

*IID* tarafından tanımlanan arabirim için sorgulandığında, COM_INTERFACE_ENTRY_AGGREGATE *punk*'ye iletir.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İçin sorgulanan arabirimin GUID 'SI.

*punk dili*<br/>
'ndaki `IUnknown` İşaretçinin adı.

### <a name="remarks"></a>Açıklamalar

*Punk* parametresinin, bir toplamanın iç Unknown değerini işaret eden veya null olan olarak kabul edilir, bu durumda giriş yok sayılır. Genellikle, `CoCreate` içinde toplamanız gerekir `FinalConstruct` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a> COM_INTERFACE_ENTRY_AGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)ile aynı, hiçbir IID sorgusunun sorgu *punk*'a iletilmesinin sonucu olduğu durumlar dışında.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Parametreler

*punk dili*<br/>
'ndaki `IUnknown` İşaretçinin adı.

### <a name="remarks"></a>Açıklamalar

Arabirim sorgusu başarısız olursa, COM haritasını işleme devam eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)ile aynı, *punk* null olması dışında, *CLSID* tarafından tanımlanan toplamı otomatik olarak oluşturur.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İçin sorgulanan arabirimin GUID 'SI.

*punk dili*<br/>
'ndaki `IUnknown` İşaretçinin adı. COM eşlemesini içeren sınıfın bir üyesi olmalıdır.

*in*<br/>
'ndaki *Punk* null ise oluşturulacak toplamanın tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

COM_INTERFACE_ENTRY_AUTOAGGREGATE ile aynı, hiçbir IID sorgusunun sorgu *punk*'a iletime ve *punk* null olması dışında, *CLSID* tarafından tanımlanan toplamı otomatik olarak oluşturan [](#com_interface_entry_autoaggregate).

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Parametreler

*punk dili*<br/>
'ndaki `IUnknown` İşaretçinin adı. COM eşlemesini içeren sınıfın bir üyesi olmalıdır.

*in*<br/>
'ndaki *Punk* null ise oluşturulacak toplamanın tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Arabirim sorgusu başarısız olursa, COM haritasını işleme devam eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a> COM_INTERFACE_ENTRY_BREAK

Belirtilen arabirim için sorgulandığında programınızın [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) ' i çağırmasını sağlar.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Arabirim tanımlayıcısını oluşturmak için kullanılan metin.

### <a name="remarks"></a>Açıklamalar

IID arabirimi *x* öğesine eklenerek oluşturulacak `IID_` . Örneğin, *x* Ise `IPersistStorage` , IID olur `IID_IPersistStorage` .

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a> COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Her örnek için arabirime özgü verileri kaydeder.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Yırma arabiriminin GUID 'SI.

*x*<br/>
'ndaki Arabirimi uygulayan sınıfın adı.

*punk dili*<br/>
'ndaki `IUnknown` İşaretçinin adı. COM eşlemesini içeren sınıfın bir üyesi olmalıdır. Sınıf nesnesinin oluşturucusunda NULL olarak başlatılmalıdır.

### <a name="remarks"></a>Açıklamalar

Arabirim kullanılmıyorsa, bu, nesnenizin genel örnek boyutunu düşürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a> COM_INTERFACE_ENTRY_TEAR_OFF

Yırma arabirimlerini gösterir.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Yırma arabiriminin GUID 'SI.

*x*<br/>
'ndaki Arabirimi uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Bir ayırıcı arabirim, her temsil ettiği arabirim için her zaman tarafından oluşturulan ayrı bir nesne olarak uygulanır. Genellikle, arabirimi nadiren kullanılıyorsa, arayüzü, ana nesnenizin her örneğine bir vtable işaretçisi kaydettiği için bir yırt olarak derleyebilirsiniz. Başvuru sayısı sıfır olduğunda, tear silinir. Yırma uygulayan sınıf ' dan türetilmiş olmalı `CComTearOffObjectBase` ve kendı com eşlemesine sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a> COM_INTERFACE_ENTRY_CHAIN

İşlem COM eşlemesinde bu girişe ulaştığında taban sınıfının COM haritasını işler.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Parametreler

*sınıf*<br/>
'ndaki Geçerli nesnenin temel sınıfı.

### <a name="remarks"></a>Açıklamalar

Örneğin, aşağıdaki kodda:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM eşlemesindeki ilk girdinin COM eşlemesini içeren nesne üzerindeki bir arabirim olması gerektiğini unutmayın. Bu nedenle, com map girdilerinizi COM_INTERFACE_ENTRY_CHAIN ile başlatamazsınız. Bu, farklı bir nesnenin com eşlemesinin, nesnenizin com eşlemesinde **COM_INTERFACE_ENTRY_CHAIN (** `COtherObject` **)** göründüğü noktada aranmasına neden olur. Önce başka bir nesnenin COM haritasını aramak isterseniz, COM haritanız için bir arabirim girişi ekleyin `IUnknown` ve ardından diğer NESNENIN com eşlemesini zincirleyebilirsiniz. Örneğin:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a> COM_INTERFACE_ENTRY_FUNC

ATL 'nin mantığını aramak için genel bir mekanizma `QueryInterface` .

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Sunulan arabirimin GUID 'SI.

*DW*<br/>
'ndaki *İşlev* işlevine geçirilen parametre.

*func*<br/>
'ndaki *IID* döndürecek işlev işaretçisi.

### <a name="remarks"></a>Açıklamalar

*IID* , için SORGULANAN arabirimin IID 'siyle eşleşiyorsa, *Func* tarafından belirtilen işlev çağrılır. İşlevin bildirimi şu olmalıdır:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

İşleviniz çağrıldığında, `pv` sınıf nesnenizin işaret eder. *Riıd* parametresi, için sorgulanmakta olan arabirimi ifade eder, `ppv` işlevin işaretçiyi arabirime depolaması gereken konumun işaretçisidir ve *DW* , girişte belirttiğiniz parametredir. İşlev \* `ppv` null olarak ayarlanmalıdır ve bir arabirim döndürmemelidir seçerse E_NOINTERFACE veya S_FALSE döndürmelidir. E_NOINTERFACE, COM eşlemesi işlemi sonlanır. S_FALSE ile, hiçbir arabirim işaretçisi döndürülmese de COM eşlemesi işleme devam eder. İşlev bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a> COM_INTERFACE_ENTRY_FUNC_BLIND

[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)ile aynıdır, ancak HERHANGI bir IID sorgusu *Func* çağrısı ile sonuçlanır.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Parametreler

*DW*<br/>
'ndaki *İşlev* işlevine geçirilen parametre.

*func*<br/>
'ndaki COM eşlemesindeki bu giriş işlendiğinde çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Herhangi bir hata, işlemin COM eşlemesinde devam etmesine neden olur. İşlev bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a> COM_INTERFACE_ENTRY_NOINTERFACE

E_NOINTERFACE döndürür ve belirtilen arabirim için sorgulandığında COM eşleme işlemesini sonlandırır.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Arabirim tanımlayıcısını oluşturmak için kullanılan metin.

### <a name="remarks"></a>Açıklamalar

Bu makroyu, bir arabirimin belirli bir durumda kullanılmasını engellemek için kullanabilirsiniz. Örneğin, arabirimin toplamanın iç bilinmediği bir sorgunun iletilmesini engellemek için COM_INTERFACE_ENTRY_AGGREGATE_BLIND önce bu makroyu COM haritanızda doğrudan ekleyebilirsiniz.

IID arabirimi *x* öğesine eklenerek oluşturulacak `IID_` . Örneğin, *x* Ise `IPersistStorage` , IID olur `IID_IPersistStorage` .
