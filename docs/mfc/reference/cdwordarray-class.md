---
title: CDWordArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDWordArray
- AFXCOLL/CDWordArray
- AFXCOLL/CDWordArray::CDWordArray
- AFXCOLL/CDWordArray::Add
- AFXCOLL/CDWordArray::Append
- AFXCOLL/CDWordArray::Copy
- AFXCOLL/CDWordArray::ElementAt
- AFXCOLL/CDWordArray::FreeExtra
- AFXCOLL/CDWordArray::GetAt
- AFXCOLL/CDWordArray::GetCount
- AFXCOLL/CDWordArray::GetData
- AFXCOLL/CDWordArray::GetSize
- AFXCOLL/CDWordArray::GetUpperBound
- AFXCOLL/CDWordArray::InsertAt
- AFXCOLL/CDWordArray::IsEmpty
- AFXCOLL/CDWordArray::RemoveAll
- AFXCOLL/CDWordArray::RemoveAt
- AFXCOLL/CDWordArray::SetAt
- AFXCOLL/CDWordArray::SetAtGrow
- AFXCOLL/CDWordArray::SetSize
helpviewer_keywords:
- CDWordArray [MFC], CDWordArray
- CDWordArray [MFC], Add
- CDWordArray [MFC], Append
- CDWordArray [MFC], Copy
- CDWordArray [MFC], ElementAt
- CDWordArray [MFC], FreeExtra
- CDWordArray [MFC], GetAt
- CDWordArray [MFC], GetCount
- CDWordArray [MFC], GetData
- CDWordArray [MFC], GetSize
- CDWordArray [MFC], GetUpperBound
- CDWordArray [MFC], InsertAt
- CDWordArray [MFC], IsEmpty
- CDWordArray [MFC], RemoveAll
- CDWordArray [MFC], RemoveAt
- CDWordArray [MFC], SetAt
- CDWordArray [MFC], SetAtGrow
- CDWordArray [MFC], SetSize
ms.assetid: 581be11e-ced6-47d1-8679-e0b8e7d99494
ms.openlocfilehash: e009ca3e3612d10d9cdf62d4bea32224f7b7522c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373993"
---
# <a name="cdwordarray-class"></a>CDWordArray Sınıfı

32 bit çift kelime dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDWordArray : public CObject
```

## <a name="members"></a>Üyeler

CObArray `CDWordArray` sınıfının üye işlevleri ne [CObArray](../../mfc/reference/cobarray-class.md)benzer. Bu benzerlik nedeniyle, üye işlev `CObArray` özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya iade `DWORD`değeri olarak gördüğünüz her yerde, bir .

`CObject* CObArray::GetAt( int <nIndex> ) const;`

örneğin, çevirir

`DWORD CDWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray::CDWordArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray::Ekle](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CDWordArray::Ek](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CDWordArray::Kopyala](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CDWordArray::elementat](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki bayt için geçici bir başvuru verir.|
|[CDWordArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CDWordArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirli bir dizindeki değeri döndürür.|
|[CDWordArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CDWordArray::Veri Alma](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|
|[CDWordArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CDWordArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CDWordArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CDWordArray::Boş](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CDWordArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CDWordArray::Removeat](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CDWordArray::Setat](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CDWordArray::Setatgrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CDWordArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray::operatör \[\]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CDWordArray`öğelerinin serileştirilmesini `IMPLEMENT_SERIAL` ve dampingini desteklemek için makroyu içerir. Bir dizi doublewords bir arşivde saklanırsa, ya aşırı yüklü **<<** ekleme ( ) `Serialize` işleci veya üye işlevi ile, her öğe sırayla, seri hale getirilir.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Dizideki tek tek öğelerden hata ayıklama çıktısına ihtiyacınız `CDumpContext` varsa, nesnenin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma `CDWordArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
