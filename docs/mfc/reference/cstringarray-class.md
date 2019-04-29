---
title: CStringArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringArray
- AFXCOLL/CStringArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
ms.openlocfilehash: 85422e5abd313aad4f87052748610e099363c1c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323784"
---
# <a name="cstringarray-class"></a>CStringArray sınıfı

Dizilerini destekler [CString](../../atl-mfc-shared/using-cstring.md) nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class CStringArray : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CStringArray` sınıfın üye işlevleri için benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObArray` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir dönüş değeri olarak alternatif bir [CString](../../atl-mfc-shared/using-cstring.md) nesne (değil bir [CString](../../atl-mfc-shared/using-cstring.md) işaretçisi). Gördüğünüz yerde bir `CObject` işaretçi işlevi parametre olarak, alternatif bir `LPCTSTR`.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, için çevirir

`CString CStringArray::GetAt( int <nIndex> ) const;`

and

`void SetAt( int <nIndex>, CObject* <newElement> )`

için çevirir

`void SetAt( int <nIndex>, LPCTSTR <newElement> )`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Diziyi başka diziye ekler; dizi gerekirse büyür.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizide öğelere erişim sağlar. Olabilir **NULL**.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki öğeyi kaldırır.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CStringArray` Serileştirme ve alt öğeleri dökme desteklemek için ımplement_serıal makrosu içerir. Bir dizi varsa `CString` nesneleri veya aşırı yüklenmiş bir ekleme operatörü ile birlikte bir arşivden depolandığı `Serialize` üye işlevi, her öğe sırayla serileştirilmiş.

> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.

Bir dizideki öğelerin tek tek dize dökümü gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

Olduğunda bir `CString` dizi silinir veya öğeleri kaldırıldığında, dize bellek uygun şekilde serbest bırakılır.

Kullanma hakkında daha fazla bilgi için `CStringArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CStringArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
