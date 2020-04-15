---
title: CUIntArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CUIntArray
- AFXCOLL/CUIntArray
- AFXCOLL/CUIntArray::CUIntArray
- AFXCOLL/CUIntArray::Add
- AFXCOLL/CUIntArray::Append
- AFXCOLL/CUIntArray::Copy
- AFXCOLL/CUIntArray::ElementAt
- AFXCOLL/CUIntArray::FreeExtra
- AFXCOLL/CUIntArray::GetAt
- AFXCOLL/CUIntArray::GetCount
- AFXCOLL/CUIntArray::GetData
- AFXCOLL/CUIntArray::GetSize
- AFXCOLL/CUIntArray::GetUpperBound
- AFXCOLL/CUIntArray::InsertAt
- AFXCOLL/CUIntArray::IsEmpty
- AFXCOLL/CUIntArray::RemoveAll
- AFXCOLL/CUIntArray::RemoveAt
- AFXCOLL/CUIntArray::SetAt
- AFXCOLL/CUIntArray::SetAtGrow
- AFXCOLL/CUIntArray::SetSize
helpviewer_keywords:
- CUIntArray [MFC], CUIntArray
- CUIntArray [MFC], Add
- CUIntArray [MFC], Append
- CUIntArray [MFC], Copy
- CUIntArray [MFC], ElementAt
- CUIntArray [MFC], FreeExtra
- CUIntArray [MFC], GetAt
- CUIntArray [MFC], GetCount
- CUIntArray [MFC], GetData
- CUIntArray [MFC], GetSize
- CUIntArray [MFC], GetUpperBound
- CUIntArray [MFC], InsertAt
- CUIntArray [MFC], IsEmpty
- CUIntArray [MFC], RemoveAll
- CUIntArray [MFC], RemoveAt
- CUIntArray [MFC], SetAt
- CUIntArray [MFC], SetAtGrow
- CUIntArray [MFC], SetSize
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
ms.openlocfilehash: 9d620269bbf6695af992feaf0df2ef1161c9ae8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373235"
---
# <a name="cuintarray-class"></a>CUIntArray Sınıfı

İmzalanmamış tümsakarışık dizileri destekler.

## <a name="syntax"></a>Sözdizimi

```
class CUIntArray : public CObject
```

## <a name="members"></a>Üyeler

CObArray `CUIntArray` sınıfının üye işlevleri ne [CObArray](../../mfc/reference/cobarray-class.md)benzer. Bu benzerlik nedeniyle, üye işlev `CObArray` özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya iade değeri olarak gördüğünüz her yerde, bir UINT değiştirin.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

örneğin, çevirir

`UINT CUIntArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CUIntArray::CUIntArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CUIntArray::Ekle](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CUIntArray::Ek](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CUIntArray::Kopyala](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CUIntArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CUIntArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CUIntArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirli bir dizindeki değeri döndürür.|
|[CUIntArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CUIntArray::Veri Alın](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|
|[CUIntArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CUIntArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CUIntArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CUIntArray::Boş](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CUIntArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CUIntArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CUIntArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CUIntArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CUIntArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CUIntArray::operatör \[\]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

İmzasız bir tamsayı veya UINT, bir UINT'nin fiziksel boyutunun hedef çalışma ortamına bağlı olarak değişebileceği sözcüklerden ve çift sözcüklerden farklıdır. UINT, çift sözcükile aynı boyuttadır.

`CUIntArray`çalışma zamanı türü erişimini ve [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesine boşaltmayı desteklemek için [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) makroyu içerir. Tek tek imzalanmamış tamsayı öğelerinin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir. İmzasız tümseci dizileri seri hale getirilemez.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Kullanma `CUIntArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CUIntArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
