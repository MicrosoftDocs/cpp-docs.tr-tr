---
title: CDWordArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDWordArray
- AFXCOLL/CDWordArray
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
ms.assetid: 581be11e-ced6-47d1-8679-e0b8e7d99494
ms.openlocfilehash: ffd4ddc94bbf35da1241b9c32069e80315e144d8
ms.sourcegitcommit: 185b8ee6dd4e10045df730c5b957b9729813da2d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2018
ms.locfileid: "53411942"
---
# <a name="cdwordarray-class"></a>CDWordArray sınıfı

32 bit doublewords dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDWordArray : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CDWordArray` sınıfın üye işlevleri için benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObArray` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlevin parametre veya dönüş değeri olarak alternatif bir `DWORD`.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, için çevirir

`DWORD CDWordArray::GetAt( int <nIndex> ) const;`

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
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içinde bayta geçici bir başvuru döndürür.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizide öğelere erişim sağlar. NULL olabilir.|
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

`CDWordArray` içerir `IMPLEMENT_SERIAL` seri hale getirme ve alt öğeleri dökme desteklemek için makrosu. Bir arşiv, aşırı yüklenmiş ekleme ile bir dizi doublewords depolanıyorsa ( **<<**) işleci veya `Serialize` üye işlevi, her öğe olan, sırayla, serileştirilmiş.

> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.

Hata ayıklama çıkışı dizi içindeki tek tek öğelerinden varsa, derinliğini ayarlamalısınız `CDumpContext` 1 veya daha büyük bir nesneye.

Kullanma hakkında daha fazla bilgi için `CDWordArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
