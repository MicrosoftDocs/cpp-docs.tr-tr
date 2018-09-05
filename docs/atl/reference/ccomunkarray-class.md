---
title: CComUnkArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b977875655182f1cbc822540cf021635f525f7e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756424"
---
# <a name="ccomunkarray-class"></a>CComUnkArray sınıfı

Bu sınıf depolar `IUnknown` işaretçileri ve bir parametre olarak kullanılmak üzere tasarlanmış [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Parametreler

*nMaxSize*  
En fazla `IUnknown` statik dizideki tutulabilir işaretçileri.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComUnkArray::Add](#add)|Eklemek için bu yöntemi çağıran bir `IUnknown` dizi için işaretçi.|
|[CComUnkArray::begin](#begin)|İlk işaretçi döndüren `IUnknown` koleksiyondaki işaretçi.|
|[CComUnkArray::end](#end)|Bir önceki son bir işaretçi döndürür `IUnknown` koleksiyondaki işaretçi.|
|[CComUnkArray::GetCookie](#getcookie)|İle ilişkili tanımlama bilgisi almak için bu yöntemi çağıran bir verilen `IUnknown` işaretçi.|
|[CComUnkArray::GetUnknown](#getunknown)|Almak için bu yöntemi çağırın `IUnknown` işaretçi verilen bir tanımlama bilgisi ile ilişkili.|
|[CComUnkArray::Remove](#remove)|Kaldırmak için bu yöntemi çağıran bir `IUnknown` işaretçisinden bir dizi.|

## <a name="remarks"></a>Açıklamalar

`CComUnkArray` sabit sayıda tutan `IUnknown` işaretçileri, her bir arabirim bir bağlantı noktası. `CComUnkArray` bir parametre olarak kullanılan [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı. `CComUnkArray<1>` bir şablon uzmanlığı olan `CComUnkArray` bir bağlantı noktası için iyileştirilmiştir.

`CComUnkArray` Yöntemleri [başlamak](#begin) ve [son](#end) tüm bağlantı noktaları (örneğin, bir olay harekete) döngü için kullanılabilir.

Bkz: [bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md) bağlantı oluşturulmasını otomatik hale getirme konusunda ayrıntılı bilgi için proxy noktası.

> [!NOTE]
> **Not** sınıfı [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) tarafından kullanılan **sınıfı Ekle** bağlantı noktaları olan bir denetim oluşturma Sihirbazı. Bağlantı noktası sayısını el ile belirtmek istiyorsanız, iş başvurusundan değiştirme `CComDynamicUnkArray` için `CComUnkArray<` *n* `>`burada *n* bağlantı noktalarının sayısı Gerekli.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="add"></a>  CComUnkArray::Add

Eklemek için bu yöntemi çağıran bir `IUnknown` dizi için işaretçi.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk*  
Eklemek için bu yöntemi çağıran bir `IUnknown` dizi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir dizi yeni işaretçi içeren büyük değilse, yeni eklenen işaretçiyi veya 0 ile ilişkili tanımlama döndürür.

##  <a name="begin"></a>  CComUnkArray::begin

Bir işaretçi koleksiyonunun başına döndürür `IUnknown` arabirim işaretçisi.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `IUnknown` arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

Koleksiyon arabirimleri olarak yerel olarak depolanan işaretçileri içeren `IUnknown`. Her dönüştürme `IUnknown` arabirim gerçek bir arabirim türüne ve arkasını çağırın. Arabirim için önce sorgu gerekmez.

Kullanmadan önce `IUnknown` arabirimi, NULL olmadığından emin denetlemelidir.

##  <a name="ccomunkarray"></a>  CComUnkArray::CComUnkArray

Oluşturucu.

```
CComUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Koleksiyonun tutmak için ayarlar `nMaxSize` `IUnknown` işaretçiler ve null işaretçilerini başlatır.

##  <a name="end"></a>  CComUnkArray::end

Bir önceki son bir işaretçi döndürür `IUnknown` koleksiyondaki işaretçi.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `IUnknown` arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CComUnkArray` Yöntemleri `begin` ve `end` tüm bağlantı noktaları, örneğin, bir olay harekete döngü için kullanılabilir.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

##  <a name="getcookie"></a>  CComUnkArray::GetCookie

İle ilişkili tanımlama bilgisi almak için bu yöntemi çağıran bir verilen `IUnknown` işaretçi.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppFind*  
`IUnknown` İşaretçi için ilişkili tanımlama bilgisi gereklidir.

### <a name="return-value"></a>Dönüş Değeri

İle ilişkili tanımlama döndürür `IUnknown` işaretçi veya eşleşen 0 `IUnknown` işaretçi bulundu.

### <a name="remarks"></a>Açıklamalar

Birden fazla örneği aynı ise `IUnknown` işaretçisiyse, bu işlev, ilk öğe için bir tanımlama bilgisi değerini döndürür.

##  <a name="getunknown"></a>  CComUnkArray::GetUnknown

Almak için bu yöntemi çağırın `IUnknown` işaretçi verilen bir tanımlama bilgisi ile ilişkili.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*  
Tanımlama bilgisi, ilişkili `IUnknown` işaretçisi gereklidir.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `IUnknown` işaretçi veya eşleşen tanımlama bilgisi bulunamazsa NULL.

##  <a name="remove"></a>  CComUnkArray::Remove

Kaldırmak için bu yöntemi çağıran bir `IUnknown` işaretçisinden bir dizi.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*  
Tanımlama bilgisi başvuru `IUnknown` işaretçi diziden kaldırılacak.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi aksi kaldırıldı, FALSE ise TRUE döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CComDynamicUnkArray sınıfı](../../atl/reference/ccomdynamicunkarray-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
