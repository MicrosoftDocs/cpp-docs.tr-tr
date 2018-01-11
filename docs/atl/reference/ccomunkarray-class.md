---
title: "CComUnkArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ca462648a43869b11984e4582c8eb2c3dfaece7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomunkarray-class"></a>CComUnkArray sınıfı
Bu sınıf depolar **IUnknown** işaretçileri ve bir parametre olarak kullanılmak üzere tasarlanmış [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Parametreler  
 *nMaxSize*  
 En fazla sayısını **IUnknown** statik dizisinde tutulabilir işaretçileri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|Eklemek için bu yöntemi çağırın bir **IUnknown** dizisine işaretçi.|  
|[CComUnkArray::begin](#begin)|İşaretçi ilk döndüren **IUnknown** koleksiyondaki işaretçi.|  
|[CComUnkArray::end](#end)|Bir son geçmiş işaretçi döndüren **IUnknown** koleksiyondaki işaretçi.|  
|[CComUnkArray::GetCookie](#getcookie)|İle ilişkili tanımlama bilgisi almak için bu yöntemi çağırın bir verilen **IUnknown** işaretçi.|  
|[CComUnkArray::GetUnknown](#getunknown)|Almak için bu yöntemi çağırın **IUnknown** belirli bir tanımlama bilgisi ile ilişkili işaretçi.|  
|[CComUnkArray::Remove](#remove)|Kaldırmak için bu yöntemi çağırın bir **IUnknown** dizisinden işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 **CComUnkArray** sabit sayıda tutan **IUnknown** işaretçileri, her bir arabirim bir bağlantı noktası. **CComUnkArray** bir parametre olarak kullanılan [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı. **CComUnkArray\<1 >** şablonu uzmanlığı olan **CComUnkArray** bir bağlantı noktası için iyileştirilmiştir.  
  
 **CComUnkArray** yöntemleri [başlamak](#begin) ve [son](#end) tüm bağlantı noktaları (örneğin, bir olay başlatıldığında) döngü için kullanılabilir.  
  
 Bkz: [ekleme bağlantı noktaları bir nesneye](../../atl/adding-connection-points-to-an-object.md) bağlantı oluşturulmasını otomatik hale getirme ile ilgili ayrıntılar için proxy noktası.  
  
> [!NOTE]
> **Not** sınıfı [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) tarafından kullanılan **sınıfı Ekle** bağlantı noktaları olan bir denetim oluştururken, Sihirbazı. Bağlantı noktası sayısı el ile belirtmek istiyorsanız, başvurusundan değiştirme **CComDynamicUnkArray** için `CComUnkArray<`  *n*  `>`, burada  *n*  gerekli bağlantı noktalarının sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="add"></a>CComUnkArray::Add  
 Eklemek için bu yöntemi çağırın bir **IUnknown** dizisine işaretçi.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 Eklemek için bu yöntemi çağırın bir **IUnknown** dizisine işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi yeni işaretçi alabilecek kadar büyük değilse yeni eklenen işaretçi veya 0 ile ilişkili tanımlama bilgisi döndürür.  
  
##  <a name="begin"></a>CComUnkArray::begin  
 Bir işaretçi koleksiyonunun başına döndürür **IUnknown** arabirim işaretçileri.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir **IUnknown** arabirim işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Koleksiyon arabirimleri olarak yerel olarak depolanan işaretçiler içerir **IUnknown**. Her cast **IUnknown** arabirim gerçek arabirim türüne ve üzerinden çağırın. Arabirim için önce sorgu gerekmez.  
  
 Kullanmadan önce **IUnknown** arabirimi, olmadığını denetlemelidir **NULL**.  
  
##  <a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 Oluşturucu.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Topluluğun tutmak için ayarlar `nMaxSize` **IUnknown** işaretçileri ve işaretçiler başlatır **NULL**.  
  
##  <a name="end"></a>CComUnkArray::end  
 Bir son geçmiş işaretçi döndüren **IUnknown** koleksiyondaki işaretçi.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir **IUnknown** arabirim işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComUnkArray` Yöntemleri **başlamak** ve **son** tüm bağlantı noktaları, örneğin, bir olay başlatıldığında döngü için kullanılabilir.  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>CComUnkArray::GetCookie  
 İle ilişkili tanımlama bilgisi almak için bu yöntemi çağırın bir verilen **IUnknown** işaretçi.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppFind`  
 **IUnknown** ilişkili tanımlama bilgisi olduğu gerekli işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İle ilişkili tanımlama bilgisi döndürür **IUnknown** işaretçi ya da eşleşme yoksa 0 **IUnknown** işaretçi bulundu.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok örneği aynı olup olmadığını **IUnknown** işaretçi, bu işlev, ilk için tanımlama bilgisi döndürür.  
  
##  <a name="getunknown"></a>CComUnkArray::GetUnknown  
 Almak için bu yöntemi çağırın **IUnknown** belirli bir tanımlama bilgisi ile ilişkili işaretçi.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCookie`  
 Kendisi için tanımlama bilgisi ilişkili **IUnknown** işaretçi gereklidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **IUnknown** işaretçi ya da eşleşen tanımlama bilgisi bulunursa, NULL.  
  
##  <a name="remove"></a>CComUnkArray::Remove  
 Kaldırmak için bu yöntemi çağırın bir **IUnknown** dizisinden işaretçi.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCookie`  
 Tanımlama bilgisi başvuran **IUnknown** diziden kaldırılacak işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** işaretçinin kaldırılırsa, **FALSE** Aksi takdirde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComDynamicUnkArray sınıfı](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
