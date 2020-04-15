---
title: Cmapstringtostring Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToString::CMapStringToString
- AFXCOLL/CMapStringToString::GetCount
- AFXCOLL/CMapStringToString::GetHashTableSize
- AFXCOLL/CMapStringToString::GetNextAssoc
- AFXCOLL/CMapStringToString::GetSize
- AFXCOLL/CMapStringToString::GetStartPosition
- AFXCOLL/CMapStringToString::HashKey
- AFXCOLL/CMapStringToString::InitHashTable
- AFXCOLL/CMapStringToString::IsEmpty
- AFXCOLL/CMapStringToString::Lookup
- AFXCOLL/CMapStringToString::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToString::RemoveAll
- AFXCOLL/CMapStringToString::RemoveKey
- AFXCOLL/CMapStringToString::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToString [MFC], CMapStringToString
- CMapStringToString [MFC], GetCount
- CMapStringToString [MFC], GetHashTableSize
- CMapStringToString [MFC], GetNextAssoc
- CMapStringToString [MFC], GetSize
- CMapStringToString [MFC], GetStartPosition
- CMapStringToString [MFC], HashKey
- CMapStringToString [MFC], InitHashTable
- CMapStringToString [MFC], IsEmpty
- CMapStringToString [MFC], Lookup
- CMapStringToString [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToString [MFC], RemoveAll
- CMapStringToString [MFC], RemoveKey
- CMapStringToString [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 544154569c50369b805ba296aa975849f245d4ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370127"
---
# <a name="cmapstringtostring-class"></a>Cmapstringtostring Sınıfı

Nesneler tarafından `CString` `CString` anahtarlanan nesnelerin eşlemlerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Üyeler

`CMapStringToString` [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzer. Bu benzerlik nedeniyle, üye işlev `CMapStringToOb` özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi iade değeri veya "çıktı" işlev parametresi olarak gördüğünüz her yerde, bir işaretçiyi **char**olarak değiştirin. `CObject` İşaretçiyi "giriş" işlev parametresi olarak gördüğünüz her yerde, bir işaretçiyi **char**olarak değiştirin.

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

örneğin, çevirir

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>Kamu Yapıları

|Adı|Açıklama|
|----------|-----------------|
|[Cmapstringtostring::cpair](#cpair)|Anahtar değeri ve ilişkili dize nesnesinin değerini içeren iç içe bir yapı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cmapstringtostring::cmapstringtostring](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Cmapstringtostring::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritadaki öğe sayısını döndürür.|
|[CMapStringToString::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapStringToString::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yinelenmenin bir sonraki öğesini alır.|
|[Cmapstringtostring::Getsize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritadaki öğe sayısını döndürür.|
|[Cmapstringtostring::Getstartposition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToString::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapStringToString::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tabloyu başharfe ait hale.|
|[Cmapstringtostring::Boş](../../mfc/reference/cmapstringtoob-class.md#isempty)|Boş eşlemi koşulu (öğe yok) için testler.|
|[CMapStringToString::Arama](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void pointer tuşuna göre geçersiz bir işaretçi arar. İşaretçi değeri, işaret aldığı varlık değil, anahtar karşılaştırması için kullanılır.|
|[CMapStringToString::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru verir.|
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Haritadaki ilk `CString` işaretçiyi alır.|
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Yinelemek için bir `CString` sonraki işaretçi alır.|
|[CMapStringToString::PLookup](#plookup)|Bir işaretçiyi, değeri belirtilen değerle eşleşen bir `CString` işaretçiye döndürür.|
|[Cmapstringtostring::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Bu haritadaki tüm öğeleri kaldırır.|
|[Cmapstringtostring::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[Cmapstringtostring::Setat](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToString::operatör \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Eşama bir öğe ekler — operatör ikamesi `SetAt`için .|

## <a name="remarks"></a>Açıklamalar

`CMapStringToString`öğelerinin serileştirilmesini `IMPLEMENT_SERIAL` ve dampingini desteklemek için makroyu içerir. Bir harita bir arşive depolanırsa, aşırı yüklenmiş ekleme ( **<<**) işleci veya `Serialize` üye işlevle her öğe sırayla seri hale getirilir.

Tek tek `CString` -  `CString` öğelerin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CMapStringToString` nesne silindiğinde veya öğeleri kaldırıldığında, `CString` nesneler uygun şekilde kaldırılır.

Daha fazla `CMapStringToString`bilgi için, makale [Koleksiyonları](../../mfc/collections.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="cmapstringtostringcpair"></a><a name="cpair"></a>Cmapstringtostring::cpair

Anahtar değeri ve ilişkili dize nesnesinin değerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu sınıf [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)içinde iç içe bir yapıdır.

Yapı iki alandan oluşur:

- `key`Anahtar türünün gerçek değeri.

- `value`İlişkili nesnenin değeri.

[Bu CMapStringToString gelen](#plookup)dönüş değerlerini depolamak için kullanılır::PLookup , [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), ve [CMapStringToString::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Örnek

  Kullanım örneği [için, CMapStringToString](#plookup)için örneğe bakın::PLookup .

## <a name="cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMapStringToString::PGetFirstAssoc

Harita nesnesinin ilk girişini döndürür.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk girişiçin bir işaretçi; bkz: [CMapStringToString::CPair](#cpair). Harita boşsa, değer NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bir işaretçiyi eşöğecitindeki ilk öğeyi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

## <a name="cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc

*pAssocRec*tarafından işaret edilen harita öğesini alır.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Parametreler

*pAssoc*<br/>
Önceki bir [PGetNextAssoc veya PGetFirstAssoc](#pgetnextassoc) çağrısı yla döndürülen bir harita girişine işaret edilir. [PGetFirstAssoc](#pgetfirstassoc)

### <a name="return-value"></a>Dönüş Değeri

Haritadaki bir sonraki girişiçin bir işaretçi; bkz: [CMapStringToString::CPair](#cpair). Öğe haritadaki son öğeyse, değer NULL'dur.

### <a name="remarks"></a>Açıklamalar

Haritadaki tüm öğeleri yinelemek için bu yöntemi çağırın. Bir çağrı ile ilk `PGetFirstAssoc` öğeyi alın ve sonra ardışık `PGetNextAssoc`aramalar ile harita üzerinden yineleyin.

### <a name="example"></a>Örnek

  [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)için örnek bakın.

## <a name="cmapstringtostringplookup"></a><a name="plookup"></a>CMapStringToString::PLookup

Belirli bir anahtara eşlenen değeri arar.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Öğenin aranması için anahtara işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara işaretçi.

### <a name="remarks"></a>Açıklamalar

Verilen anahtarla tam olarak eşleşen bir anahtara sahip bir harita öğesi aramak için bu yöntemi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
