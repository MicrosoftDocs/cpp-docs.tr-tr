---
title: "Toplama ve sınıf Fabrika makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce4021ee01052f1c830bba5ad1932898fd84b281
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="aggregation-and-class-factory-macros"></a>Toplama ve sınıf Fabrika makroları
Bu makroları toplama denetleme ve sınıf oluşturucuları bildirme yollar sağlar.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Nesnenizin olabilir bildirir (varsayılan) bir araya getirilir.|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Olmasını üreteci bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL varsayılan üreteci.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Üreteci olması için sınıf üretecini bildirir.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Bildirir [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) üreteci olmalıdır.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Bildirir [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) üreteci olmalıdır.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Bildirir [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) üreteci olmalıdır.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Bir sanal bildirir `GetControllingUnknown` işlevi.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Nesnenizin toplanamaz bildirir.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Nesnenizin toplanması gereken bildirir.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Dış bilinmeyen denetler ve nesnenizin toplanabilir veya değil toplanabilir, uygun şekilde bildirir.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Dış nesne silme işlemi sırasında bir iç nesne oluşumunu önler.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Belirtir **VIEWSTATUS** bayrakları kapsayıcısı.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Nesnenizin kümelenebilir belirtir.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Aggregatable olarak tanımlıyorsanız sınıfının adı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) varsayılan toplama modeli belirtmek için bu makrosu içerir. Bu varsayılanı geçersiz kılmak için ya da belirleyin [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) veya [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) makrosu sınıf tanımında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) üreteci olmalıdır.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) nesnenizin varsayılan üreteci bildirmek için bu makrosu kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>CComClassFactory sınıfı  
 Bu sınıf uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) arabirimi.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CComClassFactory`uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) daha hızlı oluşturulacak yeni nesneler izin vermek için bellek sınıfı fabrikada kilitleme yanı sıra belirli CLSID bir nesne oluşturmak için kullanılan yöntemler içerir arabirimi. **IClassFactory** sistem kayıt defterinde ve CLSID atamak için kayıt her sınıf için uygulanması gerekir.  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir `CComClassFactory` varsayılan üreteci olarak. Bu varsayılanı geçersiz kılmak için aşağıdakilerden birini belirtin `DECLARE_CLASSFACTORY` *XXX* Sınıf tanımınız makrolarındaki. Örneğin, [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) makrosu üreteci için belirtilen sınıf kullanır:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 Yukarıdaki sınıf tanımını belirleyen **CMyClassFactory** nesnenin varsayılan üreteci kullanılır. **CMyClassFactory** öğesinden türetilmelidir `CComClassFactory` ve geçersiz kılma `CreateInstance`.  
  
 ATL bir üreteci bildirme üç makroları sağlar:  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2) kullanan [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), bir lisans ile oluşturma denetler.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) kullanan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), birden çok grupların nesneler oluşturur.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) kullanan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), tek bir yapıları [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi.  
  
##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 Bildirir `cf` üreteci olmalıdır.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 [in] Sınıf üretecini uygulayan sınıf adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `cf` Parametresi öğesinden türetilmelidir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve geçersiz kılma `CreateInstance` yöntemi.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_CLASSFACTORY](#declare_classfactory) belirtir makrosu `CComClassFactory` varsayılan üreteci olarak. Ekleyerek ancak `DECLARE_CLASSFACTORY_EX` makrosu, nesnenin sınıf tanımında bu varsayılanı geçersiz kılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 Bildirir [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) üreteci olmalıdır.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Parametreler  
 *Lisans Sözleşmesi*  
 [in] Uygulayan bir sınıf `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`.  
  
### <a name="remarks"></a>Açıklamalar  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_CLASSFACTORY](#declare_classfactory) belirtir makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Ekleyerek ancak `DECLARE_CLASSFACTORY2` makrosu, nesnenin sınıf tanımında bu varsayılanı geçersiz kılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>CComClassFactory2 sınıfı  
 Bu sınıf uygulayan [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) arabirimi.  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>Parametreler  
 *Lisans*  
 Aşağıdaki statik işlevler uygulayan bir sınıf:  
  
- **statik BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **statik BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **statik BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>Açıklamalar  
 `CComClassFactory2`uygulayan [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) uzantısıdır arabirimi, [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** denetimleri nesne bir lisans ile oluşturma. Bir sınıf Fabrika lisanslı bir makinede yürütülen bir çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı tam makine lisans yoksa nesneleri örneği oluşturmak bir uygulama sağlar.  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Kullanılacak `CComClassFactory2`, belirtin [DECLARE_CLASSFACTORY2](#declare_classfactory2) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, şablon parametresi `CComClassFactory2`, statik işlevler uygulamalıdır `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`. Bir basit lisans sınıfın bir örnek verilmiştir:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`hem türetilen **CComClassFactory2Base** ve *lisans*. **CComClassFactory2Base**, buna karşılık, türetilen **IClassFactory2** ve **in uygulamasına\< CComGlobalsThreadModel >**.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Bildirir [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) üreteci olmalıdır.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_CLASSFACTORY](#declare_classfactory) belirtir makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Ekleyerek ancak `DECLARE_CLASSFACTORY_AUTO_THREAD` makrosu, nesnenin sınıf tanımında bu varsayılanı geçersiz kılabilir.  
  
 Nesneler (işlem dışı Server'daki) birden çok grupların oluştururken, ekleme `DECLARE_CLASSFACTORY_AUTO_THREAD` sınıfınıza.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread sınıfı  
 Bu sınıf uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) arabirim ve nesnelerin içinde birden çok grupların oluşturulmasına izin verir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CComClassFactoryAutoThread`benzer [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ancak nesnelerin içinde birden çok grupların oluşturulmasına izin verir. Bu destek yararlanmak için EXE modülünden türetin [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Kullanılacak `CComClassFactoryAutoThread`, belirtin [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Bildirir [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) üreteci olmalıdır.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Parametreler  
 `obj`  
 [in] Sınıf nesnesi adı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_CLASSFACTORY](#declare_classfactory) belirtir makrosu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Ekleyerek ancak `DECLARE_CLASSFACTORY_SINGLETON` makrosu, nesnenin sınıf tanımında bu varsayılanı geçersiz kılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton sınıfı  
 Bu sınıfın türetildiği [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturulamadı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınıza.  
  
 `CComClassFactorySingleton`türetilen [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturulamadı. Her çağrı `CreateInstance` yöntemi sadece bu nesne için bir arabirim işaretçisi sorgular.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](#declare_classfactory), hangi bildirir `CComClassFactory` varsayılan üreteci olarak. Kullanılacak `CComClassFactorySingleton`, belirtin [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Bir sanal işlev bildirir `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Derleyici hata iletisi alırsanız, nesnesine bu makrosu ekleme `GetControllingUnknown` tanımlı değil (örneğin, **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Nesnenizin toplanamaz belirtir.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Not aggregatable olarak tanımlıyorsanız sınıfı nesnesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `DECLARE_NOT_AGGREGATABLE`neden `CreateInstance` hata döndürülecek ( **CLASS_E_NOAGGREGATION**) denemesi yapılırsa, nesnenizin üzerine toplanacak.  
  
 Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_AGGREGATABLE](#declare_aggregatable) nesnenizin kümelenebilir belirtir makrosu. Bu varsayılan davranışı geçersiz kılmak için dahil `DECLARE_NOT_AGGREGATABLE` sınıf tanımında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Nesnenizin toplanması gereken belirtir.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Yalnızca aggregatable olarak tanımlıyorsanız sınıfı nesnesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `DECLARE_ONLY_AGGREGATABLE`bir hataya neden olur ( **E_FAIL**) denemesi yapılırsa **CoCreate** nesnenizin toplanmayan nesne olarak.  
  
 Varsayılan olarak, [CComCoClass](../../atl/reference/ccomcoclass-class.md) içeren [DECLARE_AGGREGATABLE](#declare_aggregatable) nesnenizin kümelenebilir belirtir makrosu. Bu varsayılan davranışı geçersiz kılmak için dahil `DECLARE_ONLY_AGGREGATABLE` sınıf tanımında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Belirleyen bir örneğini **CComPolyObject \<**  *x*  **>**  nesnenizin oluşturulduğunda oluşturulur.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Toplanabilir veya değil toplanabilir olarak tanımlama sınıfı nesnesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sırasında dış bilinmeyen değerini denetlenir. Eğer öyleyse **NULL**, **IUnknown** toplanmayan bir nesne için uygulanır. Dış bilinmeyen değilse **NULL**, **IUnknown** toplanmış olan bir nesne için uygulanır.  
  
 Kullanmanın avantajı `DECLARE_POLY_AGGREGATABLE` her ikisi de zorunda kalmamak olan `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesini işleme her iki durumda. Bu, yalnızca bir kopyasını vtable ve işlevlerin bir kopya, modülünde mevcut anlamına gelir. Vtable büyükse, bu modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesne için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.  
  
 `DECLARE_POLY_AGGREGATABLE` Tam bir denetim oluşturmak için ATL Denetim Sihirbazı'nı kullanırsanız makrosu, nesnesinde otomatik olarak bildirilmedi.  
  
##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 Nesneniz varsa silinmiş korur (sırasında [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) iç toplanmış nesne başvuru sayısı sonra azaltır 0 sayısını artırır.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Bu makrosu belirtmek için bir ATL ActiveX denetiminin denetimi sınıfta yerleştirin **VIEWSTATUS** bayrakları kapsayıcısı.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Parametreler  
 `statusFlags`  
 [in] **VIEWSTATUS** bayrakları. Bkz: [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) bayrakları listesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
