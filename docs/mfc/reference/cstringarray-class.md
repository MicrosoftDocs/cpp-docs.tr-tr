---
title: CStringArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringArray
- AFXCOLL/CStringArray
- AFXCOLL/CStringArray::CStringArray
- AFXCOLL/CStringArray::Add
- AFXCOLL/CStringArray::Append
- AFXCOLL/CStringArray::Copy
- AFXCOLL/CStringArray::ElementAt
- AFXCOLL/CStringArray::FreeExtra
- AFXCOLL/CStringArray::GetAt
- AFXCOLL/CStringArray::GetCount
- AFXCOLL/CStringArray::GetData
- AFXCOLL/CStringArray::GetSize
- AFXCOLL/CStringArray::GetUpperBound
- AFXCOLL/CStringArray::InsertAt
- AFXCOLL/CStringArray::IsEmpty
- AFXCOLL/CStringArray::RemoveAll
- AFXCOLL/CStringArray::RemoveAt
- AFXCOLL/CStringArray::SetAt
- AFXCOLL/CStringArray::SetAtGrow
- AFXCOLL/CStringArray::SetSize
helpviewer_keywords:
- CStringArray [MFC], CStringArray
- CStringArray [MFC], Add
- CStringArray [MFC], Append
- CStringArray [MFC], Copy
- CStringArray [MFC], ElementAt
- CStringArray [MFC], FreeExtra
- CStringArray [MFC], GetAt
- CStringArray [MFC], GetCount
- CStringArray [MFC], GetData
- CStringArray [MFC], GetSize
- CStringArray [MFC], GetUpperBound
- CStringArray [MFC], InsertAt
- CStringArray [MFC], IsEmpty
- CStringArray [MFC], RemoveAll
- CStringArray [MFC], RemoveAt
- CStringArray [MFC], SetAt
- CStringArray [MFC], SetAtGrow
- CStringArray [MFC], SetSize
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
ms.openlocfilehash: f5be5f44e86e3e24bc51dc014ca3c837bf5cf07d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445116"
---
# <a name="cstringarray-class"></a>CStringArray sınıfı

[CString](../../atl-mfc-shared/using-cstring.md) nesnelerinin dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CStringArray : public CObject
```

## <a name="members"></a>Üyeler

`CStringArray` üye işlevleri [CObArray](../../mfc/reference/cobarray-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, üye işlevi özellikleri için `CObArray` başvuru belgelerini kullanabilirsiniz. Dönüş değeri olarak `CObject` bir işaretçi Gördüğünüz her yerde, bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesi ( [CString](../../atl-mfc-shared/using-cstring.md) işaretçisi değil) yerine koyun. İşlev parametresi olarak `CObject` bir işaretçi Gördüğünüz her yerde, bir `LPCTSTR`yerine koyun.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, öğesine çevirir

`CString CStringArray::GetAt( int <nIndex> ) const;`

ile

`void SetAt( int <nIndex>, CObject* <newElement> )`

çevirir

`void SetAt( int <nIndex>, LPCTSTR <newElement> )`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray:: CStringArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray:: Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CStringArray:: Append](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CStringArray:: Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CStringArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CStringArray:: FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CStringArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Verilen dizindeki değeri döndürür.|
|[CStringArray:: GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CStringArray:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişime izin verir. **Null**olabilir.|
|[CStringArray:: GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CStringArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CStringArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CStringArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CStringArray:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CStringArray:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CStringArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CStringArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CStringArray:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray:: operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CStringArray`, öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu içerir. `CString` nesne dizisi bir arşive depolanıyorsa, aşırı yüklenmiş bir ekleme işleci veya `Serialize` member işleviyle birlikte her öğe sırayla serileştirilir.

> [!NOTE]
>  Bir dizi kullanmadan önce, boyutunu belirlemek ve için bellek ayırmak üzere `SetSize` kullanın. `SetSize`kullanmıyorsanız, dizine öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizideki bağımsız dize öğelerinin bir dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

`CString` bir dizi silindiğinde veya öğeleri kaldırıldığında, dize belleği uygun şekilde serbest bırakılır.

`CStringArray`kullanma hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CStringArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
