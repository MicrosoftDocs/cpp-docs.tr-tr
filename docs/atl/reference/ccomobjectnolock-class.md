---
title: CComObjectNoLock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd7f9fa0ac67592c5fca805eaa4bb4ec4b0ca153
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361486"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock sınıfı
Bu sınıf uygulayan **IUnknown** toplanmayan nesne ancak mu modülü kilit sayısı oluşturucuda artırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimi uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Oluşturucu.|  
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|Nesne üzerinde başvurusu sayısını artırır.|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|Bir işaretçi istenen arabirimi döndürür.|  
|[CComObjectNoLock::Release](#release)|Başvuru sayım nesnede azaltır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectNoLock` benzer [CComObject](../../atl/reference/ccomobject-class.md) bunu uygulayan, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanmayan nesne; ancak, `CComObjectNoLock` artırma modülü kilit oluşturucuda sayar.  
  
 ATL kullanan `CComObjectNoLock` sınıf oluşturucuları için dahili olarak. Genel olarak, size bu sınıf doğrudan kullanmaz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectNoLock::AddRef  
 Nesne üzerinde başvurusu sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock  
 Oluşturucu. Farklı [CComObject](../../atl/reference/ccomobject-class.md), modül kilit sayısı artırmaz.  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 **Geçersiz kılma\***  
 [in] Bu adlandırılmamış parametre kullanılmaz. Diğer simetrisi için mevcut **CCom *** XXX*`Object`*XXX* oluşturucular.  
  
##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock  
 Yok Edicisi.  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları ve çağrıları boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).  

  
##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi tanımlayıcısı.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`. Nesne bu arabirim desteklemiyorsa `ppvObject` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="release"></a>  CComObjectNoLock::Release  
 Başvuru sayım nesnede azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, **sürüm** tanılama için kullanışlı veya test bir değer döndürür. Olmayan hata ayıklama derlemelerinde, **sürüm** her zaman 0 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
