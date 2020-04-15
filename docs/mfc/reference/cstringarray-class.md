---
title: CStringArray Sınıfı
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
ms.openlocfilehash: 96a272cbbb76b399ed7a3db6848ab3f74a615a38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365982"
---
# <a name="cstringarray-class"></a>CStringArray Sınıfı

[CString](../../atl-mfc-shared/using-cstring.md) nesne dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CStringArray : public CObject
```

## <a name="members"></a>Üyeler

CObArray `CStringArray` sınıfının üye işlevleri ne [CObArray](../../mfc/reference/cobarray-class.md)benzer. Bu benzerlik nedeniyle, üye işlev `CObArray` özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi iade değeri olarak gördüğünüz her yerde, bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesini (CString işaretçisi değil) [değiştirin.](../../atl-mfc-shared/using-cstring.md) Bir `CObject` işaretçiyi işlev parametresi olarak `LPCTSTR`gördüğünüz her yerde, bir .

`CObject* CObArray::GetAt( int <nIndex> ) const;`

örneğin, çevirir

`CString CStringArray::GetAt( int <nIndex> ) const;`

ve

`void SetAt( int <nIndex>, CObject* <newElement> )`

çevirir

`void SetAt( int <nIndex>, LPCTSTR <newElement> )`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray::CStringArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray::Ekle](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CStringArray::Ek](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CStringArray::Kopyala](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CstringArray::elementat](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CStringArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CstringArray::Getat](../../mfc/reference/cobarray-class.md#getat)|Belirli bir dizindeki değeri döndürür.|
|[CStringArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CStringArray::Veri Get](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. **NULL**olabilir.|
|[CStringArray::Getsize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CStringArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CStringArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CstringArray::Boş](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CStringArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CstringArray::removeat](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CstringArray::Setat](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CstringArray::setatgrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CStringArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CStringArray::işleç \[\]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CStringArray`öğelerinin serileştirilmesini ve dampingini desteklemek için IMPLEMENT_SERIAL makroyu içerir. Bir dizi `CString` nesne bir arşivde, aşırı yüklü bir ekleme işleci yle veya `Serialize` üye işlevle depolanırsa, her öğe sırayla seri hale getirilir.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Dizideki tek tek dize öğelerinin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CString` dizi silindiğinde veya öğeleri kaldırıldığında, dize belleği uygun şekilde serbest bırakılır.

Kullanma `CStringArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CStringArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
