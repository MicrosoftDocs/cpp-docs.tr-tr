---
title: CComClassFactorySingleton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 754a3abd02a4a09df3e36aa9aea75c400ef00761
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton sınıfı
Bu sınıfın türetildiği [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturulamadı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınıza.  
  
 `CComClassFactorySingleton` türetilen [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturulamadı. Her çağrı `CreateInstance` yöntemi sadece bu nesne için bir arabirim işaretçisi sorgular.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Sorguları `m_spObj` için bir arabirim işaretçisi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tarafından oluşturulan nesne `CComClassFactorySingleton`.|  
  
## <a name="remarks"></a>Açıklamalar  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir `CComClassFactory` varsayılan üreteci olarak. Kullanılacak `CComClassFactorySingleton`, belirtin [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance  
 Çağrıları `QueryInterface` aracılığıyla [m_spObj](#m_spobj) bir arabirim işaretçisi alınamadı.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkOuter`  
 [in] Nesne bir toplama bir parçası olarak sonra oluşturuldu, `pUnkOuter` dış bilinmeyen olması gerekir. Aksi takdirde, `pUnkOuter` olmalıdır **NULL**.  
  
 `riid`  
 [in] İstenen arabirim IID. Varsa `pUnkOuter` olan olmayan **NULL**, `riid` olmalıdır **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppvObj` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tarafından oluşturulan nesne `CComClassFactorySingleton`.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her çağrı [CreateInstance](#createinstance) yöntemi sadece bu nesne için bir arabirim işaretçisi sorgular.  
  
 Unutmayın, geçerli form `m_spObj` biçimde önemli bir değişiklik gösterir, `CComClassFactorySingleton` ATL önceki sürümlerde çalışan Önceki sürümlerde `CComClassFactorySingleton` nesnenin oluşturulduğu sınıf fabrikası aynı zamanda sunucu başlatma sırasında. Visual C++ .NET 2003 ' nesnesi gevşek, ilk isteği oluşturulur. Bu değişiklik, erken başlatma üzerinde kullanan programlarda hatalara yol açabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 sınıfı](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
