---
title: "CComDynamicUnkArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5863c224ed47c70ce485bde3cd693c29afbfbc04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray sınıfı
Bu sınıf bir dizi depolar **IUnknown** işaretçileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Oluşturucu. Topluluk değerlerine başlatır **NULL** ve sıfır koleksiyon boyutu.|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|Eklemek için bu yöntemi çağırın bir `IUnknown` dizisine işaretçi.|  
|[CComDynamicUnkArray::begin](#begin)|İşaretçi ilk döndüren `IUnknown` koleksiyondaki işaretçi.|  
|[CComDynamicUnkArray::clear](#clear)|Dizi boşaltır.|  
|[CComDynamicUnkArray::end](#end)|Bir son geçmiş işaretçi döndüren **IUnknown** koleksiyondaki işaretçi.|  
|[CComDynamicUnkArray::GetAt](#getat)|Belirtilen dizindeki öğeyi alır.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|İle ilişkili tanımlama bilgisi almak için bu yöntemi çağırın bir verilen **IUnknown** işaretçi.|  
|[CComDynamicUnkArray::GetSize](#getsize)|Bir dizi uzunluğu, döndürür.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Almak için bu yöntemi çağırın **IUnknown** belirli bir tanımlama bilgisi ile ilişkili işaretçi.|  
|[CComDynamicUnkArray::Remove](#remove)|Kaldırmak için bu yöntemi çağırın bir **IUnknown** dizisinden işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 **CComDynamicUnkArray** dinamik olarak ayrılan bir dizi tutar **IUnknown** işaretçileri, her bir arabirim bir bağlantı noktası. **CComDynamicUnkArray** bir parametre olarak kullanılan [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.  
  
 **CComDynamicUnkArray** yöntemleri [başlamak](#begin) ve [son](#end) tüm bağlantı noktaları (örneğin, bir olay başlatıldığında) döngü için kullanılabilir.  
  
 Bkz: [ekleme bağlantı noktaları bir nesneye](../../atl/adding-connection-points-to-an-object.md) bağlantı oluşturulmasını otomatik hale getirme ile ilgili ayrıntılar için proxy noktası.  
  
> [!NOTE]
> **Not** sınıfı **CComDynamicUnkArray** tarafından kullanılan **sınıfı Ekle** bağlantı noktaları olan bir denetim oluştururken, Sihirbazı. Bağlantı noktası sayısı el ile belirtmek istiyorsanız, başvurusundan değiştirme **CComDynamicUnkArray** için `CComUnkArray<`  *n*  `>`, burada  *n*  gerekli bağlantı noktalarının sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 Eklemek için bu yöntemi çağırın bir **IUnknown** dizisine işaretçi.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 **IUnknown** işaretçi dizisine ekleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni eklenen işaretçisi ile ilişkili tanımlama döndürür.  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
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
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 Dizi boşaltır.  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 Oluşturucu.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Koleksiyon boyutu sıfır olarak ayarlar ve değerlerine başlatır **NULL**. Yok Edicisi koleksiyonu gerekirse boşaltır.  
  
##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 Yok Edicisi.  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf oluşturucu tarafından ayrılan kaynakları serbest bırakır.  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 Bir son geçmiş işaretçi döndüren **IUnknown** koleksiyondaki işaretçi.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir **IUnknown** arabirim işaretçisi.  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 Belirtilen dizindeki öğeyi alır.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi.  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 İle ilişkili tanımlama bilgisi almak için bu yöntemi çağırın bir verilen **IUnknown** işaretçi.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppFind`  
 **IUnknown** ilişkili tanımlama bilgisi olduğu gerekli işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İle ilişkili tanımlama bilgisi döndürür **IUnknown** işaretçi veya eşleşme olmaması durumunda sıfır **IUnknown** işaretçi bulundu.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok örneği aynı olup olmadığını **IUnknown** işaretçi, bu işlev, ilk için tanımlama bilgisi döndürür.  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 Bir dizi uzunluğu, döndürür.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizinin uzunluğu.  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 Almak için bu yöntemi çağırın **IUnknown** belirli bir tanımlama bilgisi ile ilişkili işaretçi.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCookie`  
 Kendisi için tanımlama bilgisi ilişkili **IUnknown** işaretçi gereklidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **IUnknown** işaretçi ya da eşleşen tanımlama bilgisi bulunursa, NULL.  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 Kaldırmak için bu yöntemi çağırın bir **IUnknown** dizisinden işaretçi.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCookie`  
 Tanımlama bilgisi başvuran **IUnknown** diziden kaldırılacak işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin kaldırılırsa, TRUE döndürür; Aksi takdirde FALSE.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComUnkArray sınıfı](../../atl/reference/ccomunkarray-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
