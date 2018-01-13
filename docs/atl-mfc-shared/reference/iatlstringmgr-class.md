---
title: "IAtlStringMgr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs: C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85b99b0b1f35ecbc35b4096ac8c2260d0a55680d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr sınıfı
Bu sınıf arabirimi temsil eden bir `CStringT` bellek yöneticisi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Ayırma](#allocate)|Yeni bir dize veri yapısı ayırmak için bu yöntemi çağırın.|  
|[Kopya](#clone)|Başka bir örneği ile kullanmak için yeni bir dize yönetici bir işaretçi dönmek için bu yöntemi çağırabilmeniz `CSimpleStringT`.|  
|[Boş](#free)|Bu yöntem bir dize veri yapısı boş çağırın.|  
|[GetNilString](#getnilstring)|Bir işaretçi döndürür `CStringData` boş dize nesneler tarafından kullanılan nesne.|  
|[Yeniden ayırma](#reallocate)|Dize veri yapısı yeniden ayırmak üzere bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim MFC bağımsız dize sınıfları tarafından kullanılan bellek yönetir; gibi [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), ve [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Bu sınıf, özel bir dize sınıfınız için bir özel bellek Yöneticisi'ni uygulamak için de kullanabilirsiniz. Daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpstr.h  
  
##  <a name="allocate"></a>IAtlStringMgr::Allocate  
 Yeni bir dize veri yapısı ayırır.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nAllocLength`  
 Yeni bellek bloğu karakter sayısı.  
  
 `nCharSize`  
 Dize Yöneticisi tarafından kullanılan karakter türü boyutu (bayt cinsinden).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğuna döndürür.  
  
> [!NOTE]
>  Hatalı bir ayırma bir özel durum atma tarafından sinyal. Bunun yerine, hatalı bir ayırma döndürerek işaret **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [IAtlStringMgr::Free](#free) veya [IAtlStringMgr::ReAllocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="clone"></a>IAtlStringMgr::Clone  
 Başka bir örneği ile kullanmak için yeni bir dize yöneticiye işaretçi döndüren `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını döndürür `IAtlStringMgr` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yaygın olarak bir dize Yöneticisi için yeni bir dize gerektiğinde çerçevesi tarafından çağrılır. Çoğu durumda, **bu** işaretçi döndürülür.  
  
 Ancak, birden çok örneği tarafından kullanılan bellek yöneticisi desteklemiyorsa, `CSimpleStringT`, paylaşılabilir dizesi yöneticisi için bir işaretçi döndürdü.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="free"></a>IAtlStringMgr::Free  
 Dize veri yapısı boşaltır.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pData`  
 Boşaltılacak bellek bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından önceden ayrılmış. belirtilen bellek bloğu boşaltır [ayırma](#allocate) veya [yeniden tahsis](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Kullanım örnekleri için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 Bir işaretçi bir dize veri yapısı boş bir dize döndürür.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CStringData` boş bir dize temsil etmek için kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir dize gösterimini döndürmek için bu işlevini çağırın.  
  
> [!NOTE]
>  Bu işlev, özel bir dize Yöneticisi uygularken, hiçbir zaman başarısız olmalıdır. Bu örneği gömerek garanti **CNilStringData** dize Yöneticisi sınıfı ve bu örnek bir işaretçi dönün.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="reallocate"></a>IAtlStringMgr::Reallocate  
 Dize veri yapısı yeniden ayırır.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pData`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
 `nAllocLength`  
 Yeni bellek bloğu karakter sayısı.  
  
 `nCharSize`  
 Dize Yöneticisi tarafından kullanılan karakter türü boyutu (bayt cinsinden).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğu başlangıcını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen mevcut bellek bloğu yeniden boyutlandırmak için bu işlevi çağırmak `pData`.  
  
 Çağrı [IAtlStringMgr::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


