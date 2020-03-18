---
title: CDWordArray sınıfı
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
ms.openlocfilehash: f17caafd01bb5ddfa49afe378bfd79652149ebd8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447341"
---
# <a name="cdwordarray-class"></a>CDWordArray sınıfı

32-bit çift sözcüklerdeki dizileri destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDWordArray : public CObject
```

## <a name="members"></a>Üyeler

`CDWordArray` üye işlevleri [CObArray](../../mfc/reference/cobarray-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, üye işlevi özellikleri için `CObArray` başvuru belgelerini kullanabilirsiniz. İşlev parametresi veya dönüş değeri olarak `CObject` bir işaretçi Gördüğünüz her yerde, bir `DWORD`yerine koyun.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, öğesine çevirir

`DWORD CDWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray:: CDWordArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray:: Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CDWordArray:: Append](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CDWordArray:: Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CDWordArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki bayta geçici bir başvuru döndürür.|
|[CDWordArray:: FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CDWordArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Verilen dizindeki değeri döndürür.|
|[CDWordArray:: GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CDWordArray:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişime izin verir. NULL olabilir.|
|[CDWordArray:: GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CDWordArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CDWordArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CDWordArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CDWordArray:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CDWordArray:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CDWordArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CDWordArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CDWordArray:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CDWordArray:: operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CDWordArray`, öğelerinin serileştirilmesi ve dökümünü desteklemek için `IMPLEMENT_SERIAL` makrosunu içerir. Bir dizi doublewords, aşırı yüklenmiş ekleme ( **<<** ) işleci veya `Serialize` member işleviyle birlikte bir arşive depolanıyorsa, her öğe sırasıyla serileştirilmiş olur.

> [!NOTE]
>  Bir dizi kullanmadan önce, boyutunu belirlemek ve için bellek ayırmak üzere `SetSize` kullanın. `SetSize`kullanmıyorsanız, dizine öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizideki ayrı öğelerden oluşan hata ayıklama gerekirse, `CDumpContext` nesnesinin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

`CDWordArray`kullanma hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
