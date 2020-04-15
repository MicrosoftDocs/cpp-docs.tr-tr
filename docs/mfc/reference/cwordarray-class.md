---
title: CWordArray Sınıfı
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
ms.openlocfilehash: 9dfb0b674d52b288ebd05bf7574f1ae05e4ed1f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365906"
---
# <a name="cwordarray-class"></a>CWordArray Sınıfı

16 bit sözcük dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CWordArray : public CObject
```

## <a name="members"></a>Üyeler

CObArray `CWordArray` sınıfının üye işlevleri ne [CObArray](../../mfc/reference/cobarray-class.md)benzer. Bu benzerlik nedeniyle, üye işlev `CObArray` özellikleri için başvuru belgelerini kullanabilirsiniz. [CObject](../../mfc/reference/cobject-class.md) işaretçisini işlev parametresi veya iade değeri olarak gördüğünüz her yerde, bir WORD'ün yerine geçin.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

örneğin, çevirir

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWordArray::CWordArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWordArray::Ekle](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CWordArray::Ek](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CWordArray::Kopyala](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CWordArray::elementat](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CWordArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CWordArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirli bir dizindeki değeri döndürür.|
|[CWordArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CWordArray::Veri Alma](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|
|[CWordArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CWordArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CWordArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CWordArray::Boş](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CWordArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CWordArray::Removeat](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CWordArray::Setat](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CWordArray::Setatgrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CWordArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CWordArray::operatör &#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CWordArray`öğelerinin serileştirilmesini ve dampingini desteklemek için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroyu içerir. Bir dizi sözcük, aşırı yüklü bir ekleme işleciyle veya [CObject:Serialize](../../mfc/reference/cobject-class.md#serialize) üye işleviyle bir arşivde depolanırsa, her öğe sırayla seri hale getirilir.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Dizideki tek tek öğelerin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma `CWordArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
