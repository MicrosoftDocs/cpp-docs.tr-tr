---
title: Iatlstringmgr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a69b2667b92b27f7310bbc70087331acd4aefaa5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880654"
---
# <a name="iatlstringmgr-class"></a>Iatlstringmgr sınıfı
Bu sınıf arabirimi temsil eder bir `CStringT` bellek yöneticisi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[ayırma](#allocate)|Yeni bir dize veri yapısı ayırmak için bu yöntemi çağırın.|  
|[Kopya](#clone)|Başka bir örneği ile kullanmak için yeni bir dize Yöneticisi için bir işaretçiyi döndürmek için bu yöntemi çağırın `CSimpleStringT`.|  
|[Ücretsiz](#free)|Boş bir dize veri yapısı için bu yöntemi çağırın.|  
|[GetNilString](#getnilstring)|Bir işaretçi döndürür `CStringData` boş dize nesneler tarafından kullanılan nesne.|  
|[Yeniden ayırma](#reallocate)|Dize veri yapısı yeniden ayırmak üzere bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim MFC bağımsız dize sınıfları tarafından kullanılan belleği yönetir; gibi [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), ve [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Bu sınıf, özel dize sınıfınız için bir özel bellek yöneticisi uygulamak için de kullanabilirsiniz. Daha fazla bilgi için [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpstr.h  
  
##  <a name="allocate"></a>  IAtlStringMgr::Allocate  
 Yeni bir dize veri yapısı ayırır.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nAllocLength*  
 Yeni bellek bloğu karakterlerin sayısı.  
  
 *nCharSize*  
 Dize Yöneticisi tarafından kullanılan karakter türü boyutu (bayt cinsinden).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni ayrılan bellek bloğu için bir işaretçi döndürür.  
  
> [!NOTE]
>  Hatalı bir ayırma, bir özel durum tarafından sinyal. Bunun yerine, hatalı bir ayırma NULL tarafından didsignal.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [IAtlStringMgr::Free](#free) veya [IAtlStringMgr::ReAllocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="clone"></a>  IAtlStringMgr::Clone  
 Başka bir örneği ile kullanmak için yeni bir dize Yöneticisi için bir işaretçi döndürür `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını döndürür `IAtlStringMgr` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yaygın olarak dize Yöneticisi için yeni bir dize gerektiğinde framework tarafından çağırılır. Çoğu durumda **bu** işaretçi döndürülür.  
  
 Ancak, birden fazla örneği tarafından kullanılan bellek yöneticisi desteklemiyorsa, `CSimpleStringT`, paylaşılabilir dize Yöneticisi için bir işaretçi döndürdü.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="free"></a>  IAtlStringMgr::Free  
 Dize veri yapısı serbest bırakır.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pData*  
 Serbest bırakılacak bellek bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bellek bloğu tarafından önceden ayrılan serbest bırakan [ayırma](#allocate) veya [yeniden tahsis](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString  
 Dize veri yapısı boş bir dize için bir işaretçi döndürür.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CStringData` boş bir dize temsil etmek için kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir dize temsilini döndürün için bu işlevi çağırın.  
  
> [!NOTE]
>  Bu işlev bir özel dize Yöneticisi'ni hayata geçirirken, hiçbir zaman başarısız olmalıdır. Bu örneği ekleyerek garanti `CNilStringData` dize manager sınıfı ve söz konusu örneğine bir işaretçi döndürür.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="reallocate"></a>  IAtlStringMgr::Reallocate  
 Dize veri yapısı yeniden ayırır.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pData*  
 Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.  
  
 *nAllocLength*  
 Yeni bellek bloğu karakterlerin sayısı.  
  
 *nCharSize*  
 Dize Yöneticisi tarafından kullanılan karakter türü boyutu (bayt cinsinden).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Mevcut bellek bloğu tarafından belirtilen yeniden boyutlandırmak için bu işlevi çağırın *pData*.  
  
 Çağrı [IAtlStringMgr::Free](#free) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
> [!NOTE]
>  Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)


