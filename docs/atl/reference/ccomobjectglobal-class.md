---
title: CComObjectGlobal sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3614962d3bebada0c63b7fe804b52efaa965c6a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal sınıfı
Bu sınıf modül bulunduğu bir başvuru sayısı yönetir, `Base` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimi uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Oluşturucu.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Bir genel uygulayan `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Bir genel uygulayan `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Bir genel uygulayan **sürüm**.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|İçeren **HRESULT** yapımı sırasında döndürülen `CComObjectGlobal` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectGlobal` Modül çağırılarak bir başvuru sayısı yönetir, `Base` nesnesi. `CComObjectGlobal` Modül bırakılmamışsa sürece nesnenizin silinmez sağlar. Tüm modül başvurusu sayısı sıfıra gittiğinde nesneniz yalnızca kaldırılır.  
  
 Örneğin, kullanarak `CComObjectGlobal`, bir sınıf üreticisi, tüm istemciler tarafından paylaşılan ortak bir genel nesne tutabilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectGlobal::AddRef  
 Nesne başvuru sayısı 1 ile artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı ve test olabilir bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `AddRef` çağrıları **_Module::Lock**, burada **_Module** genel örneğinin [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.  
  
##  <a name="ccomobjectglobal"></a>  CComObjectGlobal::CComObjectGlobal  
 Oluşturucu. Çağrıları `FinalConstruct` ve ardından ayarlar [m_hResFinalConstruct](#m_hresfinalconstruct) için `HRESULT` tarafından döndürülen `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfından türetilmemiş varsa [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), kendi sağlamalısınız `FinalConstruct` yöntemi. Yıkıcı çağrıları `FinalRelease`.  
  
##  <a name="dtor"></a>  CComObjectGlobal:: ~ CComObjectGlobal  
 Yok Edicisi.  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları ve çağrıları boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>  CComObjectGlobal::m_hResFinalConstruct  
 İçeren `HRESULT` arama gelen `FinalConstruct` oluşturma işlemi sırasında `CComObjectGlobal` nesnesi.  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>  CComObjectGlobal::QueryInterface  
 İstenen arabirim işaretçisi gösteren bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi IID tarafından tanımlanan bir işaretçi veya **NULL** arabirimi bulunmazsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `QueryInterface` Yalnızca COM eşleme tablosu arabirimlerde işler.  
  
##  <a name="release"></a>  CComObjectGlobal::Release  
 Başvuru sayım nesnesinin 1 ile azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, **sürüm** tanılama için kullanışlı ve test olabilir bir değer döndürür. Olmayan hata ayıklama derlemelerinde, **sürüm** her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, **sürüm** çağrıları **_Module::Unlock**, burada **_Module** genel örneğinin [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComObjectStack sınıfı](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
