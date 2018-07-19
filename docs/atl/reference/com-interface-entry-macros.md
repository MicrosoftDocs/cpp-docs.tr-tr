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
ms.openlocfilehash: 9fa450436bee52aa9cd13803e3bf51c6a500fa0e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883381"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY makroları  
 Bu makrolar böylece tarafından erişilebilecek bir nesnenin arabirimlerinin, COM eşlemesine girin. `QueryInterface`. Sipariş arabirimler için eşleşen bir IID sırasında edileceği COM eşlemesi girişleri sırasıdır `QueryInterface`.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|Arabirimler COM arabirimi eşlemeye girer.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|İki dal devralma belirsizliğini ortadan kaldırmak için bu makroyu kullanın.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|COM eşlemesine arabirimi girin ve kendi IID belirtmek için bu makroyu kullanın.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Aynı [COM_INTERFACE_ENTRY2](#com_interface_entry2)dışında farklı bir IID belirtebilirsiniz.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Ne zaman arabirimi tanımlanan *IID* , sorgulanan `COM_INTERFACE_ENTRY_AGGREGATE` iletir `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sorgulama için bir IID sorguya iletme sonuçları hariç, *punk*.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), eğer dışında *punk* NULL ise tarafından açıklanan toplama otomatik olarak oluşturur *CLSID*.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), sorgulama için bir IID sorguya iletme sonuçları hariç, *punk*ve eğer *punk* , NULL, otomatik olarak oluşturma tarafından açıklanan toplama *CLSID*.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Programınızı çağırmak neden [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) zaman belirtilen arabirim sorgulanan için.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Her örnek için arabirime özgü verileri kaydeder.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Etiket arabirimleri kullanıma sunar.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|İşleme bu girdiye COM eşlemesine ulaştığında temel sınıfın COM eşlemesine işler.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL'nin takma için genel bir mekanizma `QueryInterface` mantığı.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Aynı [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), sorgulama için bir IID çağrısı sonuçlanır. dışında *func*.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|E_noınterface döndürür ve belirtilen arabirim için sorgulandığında COM harita işleme sonlandırır.|  

## <a name="requirements"></a>Gereksinimler
**Başlık:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY
Arabirimler COM arabirimi eşlemeye girer.

### <a name="syntax"></a>Sözdizimi

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Parametreler

[in] bir arabirimin adını x sınıfı nesnenizin doğrudan türetir.

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
 İki dal devralma belirsizliğini ortadan kaldırmak için bu makroyu kullanın.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Bir nesneden kullanıma sunmak istediğiniz arabirimin adı.  
  
 *x2*  
 [in] Devralma dalı adını *x* sunulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, iki çift arabirim, sınıf nesneden türetirseniz kullanıma `IDispatch` beri COM_INTERFACE_ENTRY2 kullanarak `IDispatch` arabirimlerin her iki tane elde edilebilir.  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID  
 COM eşlemesine arabirimi girin ve kendi IID belirtmek için bu makroyu kullanın.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] Kullanıma sunulan arabiriminin GUID'si.  
  
 *x*  
 [in] Vtable ortaya tarafından tanımlanan arabirimi sınıfının adı *IID*.  
  
 
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID  
 Aynı [COM_INTERFACE_ENTRY2](#com_interface_entry2)dışında farklı bir IID belirtebilirsiniz.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] Arabirim için belirtiyorsanız GUID.  
  
 *x*  
 [in] Doğrudan sınıf nesnenizin öğesinden türetilen arabirimin adı.  
  
 *x2*  
 [in] Doğrudan, sınıfı nesne öğesinden türer ikinci bir arabirimin adı.  
  
##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE  
 Ne zaman arabirimi tanımlanan *IID* COM_INTERFACE_ENTRY_AGGREGATE iletir için sorgulanır *punk*.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] İçin sorgulanan arabiriminin GUID'si.  
  
 *Punk*  
 [in] Adı bir `IUnknown` işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Punk* parametresi iç bilinmeyen bir toplama veya null, bu durumda giriş noktası için yok sayıldı varsayılır. Genellikle, yaptığınız `CoCreate` toplu halde `FinalConstruct`.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sorgulama için bir IID sorguya iletme sonuçları hariç, *punk*.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Parametreler  
 *Punk*  
 [in] Adı bir `IUnknown` işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirimi sorgu başarısız olursa, COM harita işleme devam eder.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Aynı [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), eğer dışında *punk* NULL ise tarafından açıklanan toplama otomatik olarak oluşturur *CLSID*.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] İçin sorgulanan arabiriminin GUID'si.  
  
 *Punk*  
 [in] Adı bir `IUnknown` işaretçi. COM eşlemesini içeren sınıfın bir üyesi olmanız gerekir.  
  
 *CLSID*  
 [in] Tanımlayıcı oluşturulur toplamanın *punk* null.  
  
### <a name="remarks"></a>Açıklamalar  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Aynı [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), sorgulama için bir IID sorguya iletme sonuçları hariç, *punk*ve eğer *punk* , NULL, otomatik olarak oluşturma tarafından açıklanan toplama *CLSID*.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Parametreler  
 *Punk*  
 [in] Adı bir `IUnknown` işaretçi. COM eşlemesini içeren sınıfın bir üyesi olmanız gerekir.  
  
 *CLSID*  
 [in] Tanımlayıcı oluşturulur toplamanın *punk* null.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirimi sorgu başarısız olursa, COM harita işleme devam eder.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK  
 Programınızı çağırmak neden [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) zaman belirtilen arabirim sorgulanan için.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Arabirim tanımlayıcısını oluşturmak için kullanılan metin.  
  
### <a name="remarks"></a>Açıklamalar  
 IID oluşturulmasını ekleyerek arabirime *x* için `IID_`. Örneğin, varsa *x* olduğu `IPersistStorage`, IID olacaktır `IID_IPersistStorage`.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Her örnek için arabirime özgü verileri kaydeder.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] Bölünmüş arabirim GUİD'si.  
  
 *x*  
 [in] Arabirimini uygulayan sınıfın adı.  
  
 *Punk*  
 [in] Adı bir `IUnknown` işaretçi. COM eşlemesini içeren sınıfın bir üyesi olmanız gerekir. Sınıfı nesne oluşturucuda NULL olarak başlatılması gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim kullanılmıyorsa bu nesnenizin genel örnek boyutunu azaltır.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF  
 Etiket arabirimleri kullanıma sunar.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] Bölünmüş arabirim GUİD'si.  
  
 *x*  
 [in] Arabirimini uygulayan sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölünmüş arabirim arabirimi temsil eder her zaman örneği ayrı bir nesne için sorgulanır olarak uygulanır. Genellikle, arabirim da nadiren kullanılıyorsa bu ana nesnenizin her örneğinde bir vtable işaretçi kaydeder olduğundan bir bölünmüş Arabiriminizin oluşturun. Başvuru sayısı sıfır olduğunda etkinleştiriliyorken silinir. Bölünmüş uygulama sınıfı nesnesinden türetilmesi `CComTearOffObjectBase` ve kendi COM eşlemesine sahip.  
  
  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN  
 İşleme bu girdiye COM eşlemesine ulaştığında temel sınıfın COM eşlemesine işler.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Parametreler  
 *ClassName*  
 [in] Geçerli nesnenin temel sınıf.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, aşağıdaki kodda:  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 COM eşlemesi ilk giriş COM eşlemesine içeren nesnesi bir arabirimde olması gerektiğini unutmayın. Bu nedenle, farklı bir nesnenin noktada aranacak COM eşlemesine neden COM_INTERFACE_ENTRY_CHAIN ile COM eşleme girişleri başlayamaz burada **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** nesnenizin COM eşlemede görünür. COM eşlemesi başka bir nesnenin ilk arama yapmak istiyorsanız, bir arabirimi girdi ekleyin `IUnknown` COM haritanıza sonra başka bir nesnenin COM eşlemesi zincir. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC  
 ATL'nin takma için genel bir mekanizma `QueryInterface` mantığı.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] Kullanıma sunulan arabiriminin GUID'si.  
  
 *dw*  
 [in] Parametre geçirilen aracılığıyla *func*.  
  
 *FUNC*  
 [in] Döndüreceği işlev işaretçisi *IID*.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *IID* IID için sorgulanan arabirimi, daha sonra tarafından belirtilen işlevin eşleşen *func* çağrılır. İşlev bildirimi olmalıdır:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 İşlev çağrıldığında `pv` sınıfı nesnenizin işaret eder. *Riid* parametresi başvuruyor, sorgulanan arabirimine `ppv` işlevi depoladığınız arabirim işaretçisi konumunu işaretçisidir ve *dw* parametre, girişi belirtildi. İşlev ayarlamalısınız \* `ppv` NULL ve dönüş e_noınterface veya bir arabirim döndürmediğine seçerse S_FALSE. COM eşlemesi işleme e_noınterface ile sonlandırır. Hiçbir arabirim işaretçisi döndürülen olsa bile S_FALSE ile COM harita işleme, devam eder. İşlevi bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND  
 Aynı [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), sorgulama için bir IID çağrısı sonuçlanır. dışında *func*.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Parametreler  
 *dw*  
 [in] Parametre geçirilen aracılığıyla *func*.  
  
 *FUNC*  
 [in] Bu girdiye COM eşlemesine işlendiğinde çağrılan işlev.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir hata, COM haritada devam etmek işleme neden olur. İşlevi bir arabirim işaretçisi döndürürse, S_OK döndürmelidir.  
  
  
##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE  
 E_noınterface döndürür ve belirtilen arabirim için sorgulandığında COM harita işleme sonlandırır.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Arabirim tanımlayıcısını oluşturmak için kullanılan metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, belirli bir durumda kullanılan bir arabirim önlemek için kullanabilirsiniz. Örneğin, COM haritanıza arabirimi için bir sorgu için toplam'ın iç bilinmeyen iletilmelerini önleyebilirsiniz COM_INTERFACE_ENTRY_AGGREGATE_BLIND hemen önce bu makroyu ekleyebilirsiniz.  
  
 IID oluşturulmasını ekleyerek arabirime *x* için `IID_`. Örneğin, varsa *x* olduğu `IPersistStorage`, IID olacaktır `IID_IPersistStorage`.  
  
  