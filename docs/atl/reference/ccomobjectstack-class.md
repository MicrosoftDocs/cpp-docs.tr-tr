---
title: "CComObjectStack sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs: C++
helpviewer_keywords: CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a4e00fc1f703df824daf7c0f1fc5fbaed05beb32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomobjectstack-class"></a>CComObjectStack sınıfı
Bu sınıf geçici bir COM nesnesi oluşturur ve bir iskelet uygulamasıyla sağlar **IUnknown**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimi uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Oluşturucu.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|Sıfır döndürür. Hata ayıklama modunda çağırır `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](#queryinterface)|Döndürür **E_NOINTERFACE**. Hata ayıklama modunda çağırır `_ASSERTE`.|  
|[CComObjectStack::Release](#release)|Sıfır döndürür. Hata ayıklama modunda çağırır `_ASSERTE`. ~|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|İçeren **HRESULT** yapımı sırasında döndürülen `CComObjectStack` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectStack`geçici bir COM nesnesi oluşturun ve nesneyi bir iskelet uygulamasını sağlamak için kullanılan **IUnknown**. Genellikle, nesne (yığına itildiği) bir işlev içinde yerel bir değişken olarak kullanılır. İşlev tamamlandığında nesnesi yok olduğundan, başvuru sayımı verimliliğini artırmak için yapılmaz.  
  
 Aşağıdaki örnek, bir işlev içinde kullanılan bir COM nesnesinin nasıl oluşturulacağını gösterir:  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 Geçici nesne `Tempobj` yığına gönderilir ve işlev bittiğinde otomatik olarak kaldırılır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>CComObjectStack::AddRef  
 Sıfır döndürür.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama modunda çağırır `_ASSERTE`.  
  
##  <a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 Oluşturucu.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları `FinalConstruct` ve ardından ayarlar [m_hResFinalConstruct](#m_hresfinalconstruct) için `HRESULT` tarafından döndürülen `FinalConstruct`. Taban sınıfından türetilmemiş varsa [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), kendi sağlamalısınız `FinalConstruct` yöntemi. Yıkıcı çağrıları `FinalRelease`.  
  
##  <a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 Yok Edicisi.  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları ve çağrıları boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 İçeren `HRESULT` arama öğesinden döndürülen `FinalConstruct` oluşturma işlemi sırasında `CComObjectStack` nesnesi.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectStack::QueryInterface  
 Döndürür **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama modunda çağırır `_ASSERTE`.  
  
##  <a name="release"></a>CComObjectStack::Release  
 Sıfır döndürür.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama modunda çağırır `_ASSERTE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal sınıfı](../../atl/reference/ccomobjectglobal-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
