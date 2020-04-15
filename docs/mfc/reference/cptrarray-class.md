---
title: CPtrArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPtrArray
- AFXCOLL/CPtrArray
- AFXCOLL/CPtrArray::CPtrArray
- AFXCOLL/CPtrArray::Add
- AFXCOLL/CPtrArray::Append
- AFXCOLL/CPtrArray::Copy
- AFXCOLL/CPtrArray::ElementAt
- AFXCOLL/CPtrArray::FreeExtra
- AFXCOLL/CPtrArray::GetAt
- AFXCOLL/CPtrArray::GetCount
- AFXCOLL/CPtrArray::GetData
- AFXCOLL/CPtrArray::GetSize
- AFXCOLL/CPtrArray::GetUpperBound
- AFXCOLL/CPtrArray::InsertAt
- AFXCOLL/CPtrArray::IsEmpty
- AFXCOLL/CPtrArray::RemoveAll
- AFXCOLL/CPtrArray::RemoveAt
- AFXCOLL/CPtrArray::SetAt
- AFXCOLL/CPtrArray::SetAtGrow
- AFXCOLL/CPtrArray::SetSize
helpviewer_keywords:
- CPtrArray [MFC], CPtrArray
- CPtrArray [MFC], Add
- CPtrArray [MFC], Append
- CPtrArray [MFC], Copy
- CPtrArray [MFC], ElementAt
- CPtrArray [MFC], FreeExtra
- CPtrArray [MFC], GetAt
- CPtrArray [MFC], GetCount
- CPtrArray [MFC], GetData
- CPtrArray [MFC], GetSize
- CPtrArray [MFC], GetUpperBound
- CPtrArray [MFC], InsertAt
- CPtrArray [MFC], IsEmpty
- CPtrArray [MFC], RemoveAll
- CPtrArray [MFC], RemoveAt
- CPtrArray [MFC], SetAt
- CPtrArray [MFC], SetAtGrow
- CPtrArray [MFC], SetSize
ms.assetid: c23b87a3-bf84-49d6-a66b-61e999d0938a
ms.openlocfilehash: 7bab68fcbd2cfa4cfe44b0fcd2a1f78af886533d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363988"
---
# <a name="cptrarray-class"></a>CPtrArray Sınıfı

Geçersiz işaretçiler dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CPtrArray : public CObject
```

## <a name="members"></a>Üyeler

CObArray `CPtrArray` sınıfının üye işlevleri ne [CObArray](../../mfc/reference/cobarray-class.md)benzer. Bu benzerlik nedeniyle, üye işlev `CObArray` özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya iade değeri olarak gördüğünüz her yerde, bir işaretçiyi **geçersiz**kılmak için değiştirin.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

örneğin, çevirir

`void* CPtrArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPtrArray::CPtrArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPtrArray::Ekle](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CPtrArray::Ek](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CPtrArray::Kopyala](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CPtrArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CPtrArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CPtrArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirli bir dizindeki değeri döndürür.|
|[CPtrArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CPtrArray::Veri Alın](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. `NULL`Olabilir.|
|[CPtrArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CPtrArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CPtrArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CPtrArray::Boş](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CPtrArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CPtrArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CPtrArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CPtrArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CPtrArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CPtrArray::operatör \[\]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CPtrArray`çalışma zamanı türü erişimini ve bir `CDumpContext` nesneye döküme destek vermek için IMPLEMENT_DYNAMIC makroyu içerir. Tek tek işaretçi dizi öğelerinin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

İşaretçi dizileri seri hale getirilemez.

Bir işaretçi dizisi silindiğinde veya öğeleri kaldırıldığında, başvurulan varlıklar değil, yalnızca işaretçiler kaldırılır.

Kullanma `CPtrArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CPtrArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
