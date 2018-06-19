---
title: COM arabirimi giriş makroları | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c3ba41a05813c4112c1e5dd51bfe447d2c8debf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366594"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY makroları  
 Tarafından erişilebilecek şekilde bu makroları nesnenin arabirimleri, COM eşlemeye girin `QueryInterface`. Bir eşleştirme için sipariş arabirimleri denetlenecektir COM eşlemesi girişlerinde sırasıdır **IID** sırasında `QueryInterface`.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|Arabirimleri COM arabirimi eşlemeye girer.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Devralma iki dalı belirsizliğini ortadan kaldırmak için bu makrosu kullanın.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|COM eşlemeye arabirimi girin ve onun IID belirtmek için bu makrosu kullanın.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Aynı [COM_INTERFACE_ENTRY2](#com_interface_entry2), farklı IID belirtebilirsiniz dışında.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Ne zaman arabirimi tanımlanan `iid` için sorgulanan `COM_INTERFACE_ENTRY_AGGREGATE` iletir `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), tüm IID için sorgulama sorguya iletme sonuçları dışında `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), eğer dışında `punk` olan **NULL**, tarafından açıklanan toplama otomatik olarak oluşturur `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)herhangi IID için sorgulama sorguya iletme sonuçları dışında `punk`ve `punk` olan **NULL**, otomatik olarak oluşturma Toplama açıklanan tarafından `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Çağrılacak programınızı neden [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) zaman belirtilen arabirim sorgulanan için.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Her örneğin arabirimi özgü verileri kaydeder.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Etiketleri arabirimlerinizi kullanıma sunar.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|İşleme COM eşlemesi bu girişi ulaştığında temel sınıfın COM eşlemesi işler.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL ait takma için genel bir mekanizma `QueryInterface` mantığı.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Aynı [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), tüm IID için sorgulama için bir çağrı sonuçlanır. ancak bu `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Döndürür **E_NOINTERFACE** ve belirtilen arabirim için sorgulandığında COM harita işleme sona erer.|  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY
Arabirimleri COM arabirimi eşlemeye girer.

### <a name="syntax"></a>Sözdizimi

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Parametreler

x [] bir arabirim adı sınıfı nesnenizin doğrudan türetir.

### <a name="remarks"></a>Açıklamalar
Genellikle, en sık kullandığınız giriş türü budur.

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
  
##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2  
 Devralma iki dalı belirsizliğini ortadan kaldırmak için bu makrosu kullanın.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Nesneden kullanıma sunmak istediğiniz bir arabirim adı.  
  
 `x2`  
 [in] İçinden devralma dalın adı *x* sunulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, iki çift arabirimler, sınıf nesnesinden türetirseniz ortaya `IDispatch` kullanarak `COM_INTERFACE_ENTRY2` beri `IDispatch` arabirimler birini elde edilebilir.  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID  
 COM eşlemeye arabirimi girin ve onun IID belirtmek için bu makrosu kullanın.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Açık arabirim GUID.  
  
 *x*  
 [in] Vtable ortaya tarafından tanımlanan arabirimi olarak sınıfın adını `iid`.  
  
 
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID  
 Aynı [COM_INTERFACE_ENTRY2](#com_interface_entry2), farklı IID belirtebilirsiniz dışında.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Arabirim için belirtme GUID.  
  
 *x*  
 [in] Sınıf nesnesi doğrudan türeyen bir arabirim adı.  
  
 `x2`  
 [in] Sınıf nesnesi doğrudan türetilen ikinci bir arabirim adı.  
  
##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE  
 Ne zaman arabirimi tanımlanan `iid` için sorgulanan `COM_INTERFACE_ENTRY_AGGREGATE` iletir `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İçin sorgulanan arabirimi GUID.  
  
 `punk`  
 [in] Adı bir **IUnknown** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `punk` Parametre iç bilinmeyen bir toplama veya çok işaret edecek şekilde varsayılır **NULL**, giriş, bu durumda yoksayılır. Genellikle, yaptığınız **CoCreate** toplama `FinalConstruct`.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), tüm IID için sorgulama sorguya iletme sonuçları dışında `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Parametreler  
 `punk`  
 [in] Adı bir **IUnknown** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim sorgu başarısız olursa, COM harita işleme devam eder.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), eğer dışında `punk` olan **NULL**, tarafından açıklanan toplama otomatik olarak oluşturur `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İçin sorgulanan arabirimi GUID.  
  
 `punk`  
 [in] Adı bir **IUnknown** işaretçi. COM eşlemesi içeren sınıf üyesi olması gerekir.  
  
 `clsid`  
 [in] Oluşturulacak toplama tanıtıcısı `punk` olan **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)herhangi IID için sorgulama sorguya iletme sonuçları dışında `punk`ve `punk` olan **NULL**, otomatik olarak oluşturma Toplama açıklanan tarafından `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Parametreler  
 `punk`  
 [in] Adı bir **IUnknown** işaretçi. COM eşlemesi içeren sınıf üyesi olması gerekir.  
  
 `clsid`  
 [in] Oluşturulacak toplama tanıtıcısı `punk` olan **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim sorgu başarısız olursa, COM harita işleme devam eder.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK  
 Çağrılacak programınızı neden [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) zaman belirtilen arabirim sorgulanan için.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Arabirim tanımlayıcısı oluşturmak için kullanılan metin.  
  
### <a name="remarks"></a>Açıklamalar  
 IID oluşturulmasını ekleyerek arabirimi *x* için `IID_`. Örneğin, varsa *x* olan `IPersistStorage`, IID olacaktır `IID_IPersistStorage`.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Her örneğin arabirimi özgü verileri kaydeder.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Etiketleri arabirimi GUID.  
  
 *x*  
 [in] Arabirimini uygulayan sınıf adı.  
  
 `punk`  
 [in] Adı bir **IUnknown** işaretçi. COM eşlemesi içeren sınıf üyesi olması gerekir. İçin başlatılacağı **NULL** sınıfı nesnenin oluşturucuda.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim kullanılmıyorsa bu nesnenizin genel örnek boyutunu düşürür.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF  
 Etiketleri arabirimlerinizi kullanıma sunar.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Etiketleri arabirimi GUID.  
  
 *x*  
 [in] Arabirimini uygulayan sınıf adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Etiketleri arabirimi arabirimi temsil ettiği her zaman, örneği ayrı bir nesne için sorgulanan olarak uygulanır. Genellikle, bu ana nesnenizin her örnekte bir vtable işaretçi kaydeder olduğundan arabirimi nadiren, kullanılıyorsa bir etiketleri Arabiriminizin oluşturun. Başvuru sayısı sıfır olduğunda etiketleri silinir. Etiketleri uygulayan sınıfa türetilmiş `CComTearOffObjectBase` ve kendi COM eşlemesi.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN  
 İşleme COM eşlemesi bu girişi ulaştığında temel sınıfın COM eşlemesi işler.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Parametreler  
 *ClassName*  
 [in] Geçerli nesnenin temel sınıf.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, aşağıdaki kod:  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 COM eşlemesi ilk giriş COM eşleme içeren nesne üzerinde bir arabirim olması gerektiğini unutmayın. Bu nedenle, COM harita girişlerinizi ile başlayamaz `COM_INTERFACE_ENTRY_CHAIN`, bir noktada aranması için farklı bir nesne COM haritasını neden olan nerede **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** nesnenin COM eşlemesinde görüntülenir. Başka bir nesnenin COM eşlemesi ilk arama yapmak istiyorsanız, bir arabirim girdisi ekleyin **IUnknown** COM eşlemenizi sonra diğer nesnenin COM eşlemesi zincir. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC  
 ATL ait takma için genel bir mekanizma `QueryInterface` mantığı.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Açık arabirim GUID.  
  
 `dw`  
 [in] Bir parametre geçirildi aracılığıyla `func`.  
  
 `func`  
 [in] Döndürülecek işlev işaretçisi `iid`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *IID* için sorgulanan arabirimi, daha sonra tarafından belirtilen işlevin IID eşleşen `func` olarak adlandırılır. İşlev bildirimi olmalıdır:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 İşlevinizi çağrıldığında `pv` sınıfı nesneye işaret eder. `riid` Parametresi başvuruyor, sorgulanan arabirimine `ppv` işaretçidir işlevi depoladığınız arabirimi işaretçisine konuma ve `dw` girdisinde belirtilen parametresi. Set işlevi \* `ppv` için **NULL** ve geri dönüp **E_NOINTERFACE** veya **S_FALSE** bir arabirim iade değil seçerse. İle **E_NOINTERFACE**, COM eşleme işlemi sonlandırır. İle **S_FALSE**, hiçbir arabirim işaretçisi döndürüldü olsa bile COM harita devam ettirir. İşlevi bir arabirim işaretçisi durumunda döndürür, döndürme zorunluluğu `S_OK`.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND  
 Aynı [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), tüm IID için sorgulama için bir çağrı sonuçlanır. ancak bu `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Parametreler  
 `dw`  
 [in] Bir parametre geçirildi aracılığıyla `func`.  
  
 `func`  
 [in] Bu giriş COM eşlemesindeki işlendiğinde çağrılan işlev.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir hata COM haritada devam etmek işleme neden olur. İşlevi bir arabirim işaretçisi durumunda döndürür, döndürme zorunluluğu `S_OK`.  
  
  
##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE  
 Döndürür **E_NOINTERFACE** ve belirtilen arabirim için sorgulandığında COM harita işleme sona erer.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Arabirim tanımlayıcısı oluşturmak için kullanılan metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir durumda kullanılan bir arabirim önlemek için bu makrosu kullanabilirsiniz. Örneğin, bu makrosu, COM ekleyebilirsiniz eşleme hemen önce `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` toplama işlevinde'nın iç bilinmeyen iletilen arabirimi için bir sorgu önlemek için.  
  
 IID oluşturulmasını ekleyerek arabirimi *x* için `IID_`. Örneğin, varsa *x* olan `IPersistStorage`, IID olacaktır `IID_IPersistStorage`.  
  
  