---
description: 'Daha fazla bilgi edinin: CWordArray sınıfı'
title: CWordArray sınıfı
ms.date: 09/07/2019
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CWordArray::CWordArray
- AFXCOLL/CWordArray::Add
- AFXCOLL/CWordArray::Append
- AFXCOLL/CWordArray::Copy
- AFXCOLL/CWordArray::ElementAt
- AFXCOLL/CWordArray::FreeExtra
- AFXCOLL/CWordArray::GetAt
- AFXCOLL/CWordArray::GetCount
- AFXCOLL/CWordArray::GetData
- AFXCOLL/CWordArray::GetSize
- AFXCOLL/CWordArray::GetUpperBound
- AFXCOLL/CWordArray::InsertAt
- AFXCOLL/CWordArray::IsEmpty
- AFXCOLL/CWordArray::RemoveAll
- AFXCOLL/CWordArray::RemoveAt
- AFXCOLL/CWordArray::SetAt
- AFXCOLL/CWordArray::SetAtGrow
- AFXCOLL/CWordArray::SetSize
helpviewer_keywords:
- CWordArray [MFC], CWordArray
- CWordArray [MFC], Add
- CWordArray [MFC], Append
- CWordArray [MFC], Copy
- CWordArray [MFC], ElementAt
- CWordArray [MFC], FreeExtra
- CWordArray [MFC], GetAt
- CWordArray [MFC], GetCount
- CWordArray [MFC], GetData
- CWordArray [MFC], GetSize
- CWordArray [MFC], GetUpperBound
- CWordArray [MFC], InsertAt
- CWordArray [MFC], IsEmpty
- CWordArray [MFC], RemoveAll
- CWordArray [MFC], RemoveAt
- CWordArray [MFC], SetAt
- CWordArray [MFC], SetAtGrow
- CWordArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
ms.openlocfilehash: 3e315a3da44b1b40a14d19014b9c967aa85c3bda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220415"
---
# <a name="cwordarray-class"></a>CWordArray sınıfı

16-bit sözcüklerdeki dizileri destekler.

## <a name="syntax"></a>Syntax

```
class CWordArray : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri `CWordArray` [CObArray](../../mfc/reference/cobarray-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CObArray` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir [CObject](../../mfc/reference/cobject-class.md) işaretçisini işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, bir kelime yerine koyun.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, öğesine çevirir

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWordArray:: CWordArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWordArray:: Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CWordArray:: Append](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CWordArray:: Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CWordArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CWordArray:: FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CWordArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Verilen dizindeki değeri döndürür.|
|[CWordArray:: GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CWordArray:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişime izin verir. NULL olabilir.|
|[CWordArray:: GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CWordArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CWordArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CWordArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CWordArray:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CWordArray:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CWordArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CWordArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CWordArray:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CWordArray:: operator &#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CWordArray` öğelerinin serileştirilmesi ve dökümünü desteklemek için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu ekler. Bir sözcük dizisi, aşırı yüklenmiş bir ekleme işleci veya [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevi ile bir arşive depolanıyorsa, her öğe sırasıyla serileştirilmiş olur.

> [!NOTE]
> Bir dizi kullanmadan önce, `SetSize` boyutunu belirlemek ve için bellek ayırmak üzere kullanın. Kullanmıyorsanız `SetSize` , diziye öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizideki ayrı öğelerin bir dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma hakkında daha fazla bilgi için `CWordArray` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
