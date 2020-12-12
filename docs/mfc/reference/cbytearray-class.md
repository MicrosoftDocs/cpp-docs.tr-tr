---
description: 'Daha fazla bilgi edinin: CByteArray sınıfı'
title: CByteArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CByteArray
- AFXCOLL/CByteArray
- AFXCOLL/CByteArray::CByteArray
- AFXCOLL/CByteArray::Add
- AFXCOLL/CByteArray::Append
- AFXCOLL/CByteArray::Copy
- AFXCOLL/CByteArray::ElementAt
- AFXCOLL/CByteArray::FreeExtra
- AFXCOLL/CByteArray::GetAt
- AFXCOLL/CByteArray::GetCount
- AFXCOLL/CByteArray::GetData
- AFXCOLL/CByteArray::GetSize
- AFXCOLL/CByteArray::GetUpperBound
- AFXCOLL/CByteArray::InsertAt
- AFXCOLL/CByteArray::IsEmpty
- AFXCOLL/CByteArray::RemoveAll
- AFXCOLL/CByteArray::RemoveAt
- AFXCOLL/CByteArray::SetAt
- AFXCOLL/CByteArray::SetAtGrow
- AFXCOLL/CByteArray::SetSize
helpviewer_keywords:
- CByteArray [MFC], CByteArray
- CByteArray [MFC], Add
- CByteArray [MFC], Append
- CByteArray [MFC], Copy
- CByteArray [MFC], ElementAt
- CByteArray [MFC], FreeExtra
- CByteArray [MFC], GetAt
- CByteArray [MFC], GetCount
- CByteArray [MFC], GetData
- CByteArray [MFC], GetSize
- CByteArray [MFC], GetUpperBound
- CByteArray [MFC], InsertAt
- CByteArray [MFC], IsEmpty
- CByteArray [MFC], RemoveAll
- CByteArray [MFC], RemoveAt
- CByteArray [MFC], SetAt
- CByteArray [MFC], SetAtGrow
- CByteArray [MFC], SetSize
ms.assetid: 53d4a512-657c-4187-9609-e3f5339a78e0
ms.openlocfilehash: dd1c354fa380d9eba808fb808ebfffc3b861c3bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122531"
---
# <a name="cbytearray-class"></a>CByteArray sınıfı

, Dinamik bayt dizilerini destekler.

## <a name="syntax"></a>Syntax

```
class CByteArray : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri `CByteArray` [CObArray](../../mfc/reference/cobarray-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CObArray` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işlevi işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, BIR bayt yerine koyun.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, öğesine çevirir

`BYTE CByteArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CByteArray:: CByteArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CByteArray:: Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CByteArray:: Append](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CByteArray:: Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CByteArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki bayta geçici bir başvuru döndürür.|
|[CByteArray:: FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CByteArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Verilen dizindeki değeri döndürür.|
|[CByteArray:: GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CByteArray:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişime izin verir. NULL olabilir.|
|[CByteArray:: GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CByteArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CByteArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CByteArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CByteArray:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CByteArray:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CByteArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CByteArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CByteArray:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CByteArray:: işleci \[\]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CByteArray` öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu ekler. Bir bayt dizisi, aşırı yüklenmiş ekleme ( **<<** ) işleci veya üye işlevi ile bir arşive depolanıyorsa, `Serialize` her öğe sırayla, serileştirilmiş olur.

> [!NOTE]
> Bir dizi kullanmadan önce, `SetSize` boyutunu belirlemek ve için bellek ayırmak üzere kullanın. Kullanmıyorsanız `SetSize` , diziye öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizideki ayrı öğelerden oluşan hata ayıklama gerekirse, `CDumpContext` nesnenin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma hakkında daha fazla bilgi için `CByteArray` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CByteArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray sınıfı](../../mfc/reference/cobarray-class.md)
