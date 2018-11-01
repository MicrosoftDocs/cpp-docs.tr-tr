---
title: CComDynamicUnkArray sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: c18f28cac89288096b812635e77194bfb5dd224b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448691"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray sınıfı

Bu sınıf, bir dizi depolar `IUnknown` işaretçileri.

## <a name="syntax"></a>Sözdizimi

```
class CComDynamicUnkArray
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Oluşturucu. Toplama değerleri null ve koleksiyon boyutu sıfırdan başlatır.|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|Eklemek için bu yöntemi çağıran bir `IUnknown` dizi için işaretçi.|
|[CComDynamicUnkArray::begin](#begin)|İlk işaretçi döndüren `IUnknown` koleksiyondaki işaretçi.|
|[CComDynamicUnkArray::clear](#clear)|Dizi boşaltır.|
|[CComDynamicUnkArray::end](#end)|Bir önceki son bir işaretçi döndürür `IUnknown` koleksiyondaki işaretçi.|
|[CComDynamicUnkArray::GetAt](#getat)|Belirtilen dizindeki öğeyi alır.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|İle ilişkili tanımlama bilgisi almak için bu yöntemi çağıran bir verilen `IUnknown` işaretçi.|
|[CComDynamicUnkArray::GetSize](#getsize)|Dizinin uzunluğunu döndürür.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Almak için bu yöntemi çağırın `IUnknown` işaretçi verilen bir tanımlama bilgisi ile ilişkili.|
|[CComDynamicUnkArray::Remove](#remove)|Kaldırmak için bu yöntemi çağıran bir `IUnknown` işaretçisinden bir dizi.|

## <a name="remarks"></a>Açıklamalar

`CComDynamicUnkArray` dinamik olarak ayrılan dizi tutar `IUnknown` işaretçileri, her bir arabirim bir bağlantı noktası. `CComDynamicUnkArray` bir parametre olarak kullanılan [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.

`CComDynamicUnkArray` Yöntemleri [başlamak](#begin) ve [son](#end) tüm bağlantı noktaları (örneğin, bir olay harekete) döngü için kullanılabilir.

Bkz: [bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md) bağlantı oluşturulmasını otomatik hale getirme konusunda ayrıntılı bilgi için proxy noktası.

> [!NOTE]
> **Not** sınıfı `CComDynamicUnkArray` tarafından kullanılan **sınıfı Ekle** bağlantı noktaları olan bir denetim oluşturma Sihirbazı. Bağlantı noktası sayısını el ile belirtmek istiyorsanız, iş başvurusundan değiştirme `CComDynamicUnkArray` için `CComUnkArray<` *n* `>`burada *n* bağlantı noktalarının sayısı Gerekli.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="add"></a>  CComDynamicUnkArray::Add

Eklemek için bu yöntemi çağıran bir `IUnknown` dizi için işaretçi.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk*<br/>
`IUnknown` Diziye eklemek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen işaretçisi ile ilişkili tanımlama bilgisini döndürür.

##  <a name="begin"></a>  CComDynamicUnkArray::begin

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

##  <a name="clear"></a>  CComDynamicUnkArray::clear

Dizi boşaltır.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray

Oluşturucu.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Koleksiyon boyutu sıfır olarak ayarlıyor ve NULL değerlere başlatır. Gerekirse koleksiyon yok Edicisi serbest bırakır.

##  <a name="dtor"></a>  CComDynamicUnkArray:: ~ CComDynamicUnkArray

Yıkıcı.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucu tarafından ayrılan kaynakları serbest bırakır.

##  <a name="end"></a>  CComDynamicUnkArray::end

Bir önceki son bir işaretçi döndürür `IUnknown` koleksiyondaki işaretçi.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `IUnknown` arabirim işaretçisi.

##  <a name="getat"></a>  CComDynamicUnkArray::GetAt

Belirtilen dizindeki öğeyi alır.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) arabirimi.

##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie

İle ilişkili tanımlama bilgisi almak için bu yöntemi çağıran bir verilen `IUnknown` işaretçi.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppFind*<br/>
`IUnknown` İşaretçi için ilişkili tanımlama bilgisi gereklidir.

### <a name="return-value"></a>Dönüş Değeri

İle ilişkili tanımlama döndürür `IUnknown` işaretçi veya eşleşme olursa sıfır `IUnknown` işaretçi bulundu.

### <a name="remarks"></a>Açıklamalar

Birden fazla örneği aynı ise `IUnknown` işaretçisiyse, bu işlev, ilk öğe için bir tanımlama bilgisi değerini döndürür.

##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize

Dizinin uzunluğunu döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin uzunluğu.

##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown

Almak için bu yöntemi çağırın `IUnknown` işaretçi verilen bir tanımlama bilgisi ile ilişkili.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Tanımlama bilgisi, ilişkili `IUnknown` işaretçisi gereklidir.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `IUnknown` işaretçi veya eşleşen tanımlama bilgisi bulunamazsa NULL.

##  <a name="remove"></a>  CComDynamicUnkArray::Remove

Kaldırmak için bu yöntemi çağıran bir `IUnknown` işaretçisinden bir dizi.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Tanımlama bilgisi başvuru `IUnknown` işaretçi diziden kaldırılacak.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa, TRUE döndürür; Aksi durumda FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[CComUnkArray Sınıfı](../../atl/reference/ccomunkarray-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
