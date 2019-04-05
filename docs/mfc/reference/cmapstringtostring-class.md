---
title: CMapStringToString sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: ed717497866076681e39cdee7803a45eb8e097d3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780372"
---
# <a name="cmapstringtostring-class"></a>CMapStringToString sınıfı

Haritalarını destekler `CString` Anahtarlanan `CString` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CMapStringToString` sınıfın üye işlevleri için benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CMapStringToOb` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi parametresi, dönüş değeri veya "çıkış" işlevi olarak alternatif bir işaretçiye **char**. Gördüğünüz yerde bir `CObject` işaretçi bir "Giriş" işlevi parametre olarak bir işaretçiye yerine **char**.

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

Örneğin, için çevirir

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

### <a name="public-structures"></a>Genel yapılar

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToString::CPair](#cpair)|Bir anahtar değeri ve ilişkili dize nesnenin değerini içeren bir iç içe geçmiş yapısı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Geçerli bir karma tablo içindeki öğelerin sayısını belirler.|
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen bir anahtarı karma değerini hesaplar.|
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tablo başlatır.|
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|(Öğe yok) boş-map koşulu sınar.|
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void bir işaretçi void işaretçisine anahtara göre arar. İşaretçi değeri değil, işaret varlık anahtar karşılaştırma için kullanılır.|
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.|
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Öncelikle bir işaretçi alır `CString` haritadaki.|
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Sonraki bir işaretçi alır `CString` yineleme.|
|[CMapStringToString::PLookup](#plookup)|Bir işaretçi döndüren bir `CString` değeri belirtilen değerle eşleşmektedir.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritayı bir öğe ekler; eşleşen bir anahtar bulunursa, var olan öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Haritayı bir öğe ekler; işleci alternatifi için `SetAt`.|

## <a name="remarks"></a>Açıklamalar

`CMapStringToString` içerir `IMPLEMENT_SERIAL` seri hale getirme ve alt öğeleri dökme desteklemek için makrosu. Bir eşleme bir arşiv, aşırı yüklenmiş ekleme ile depolanıyorsa her öğesi sırayla seri ( **<<**) işleci veya `Serialize` üye işlevi.

Tek bir dökümü gerekiyorsa `CString` -  `CString` öğeleri ayarlamanız gerekir döküm bağlam derinliğini 1 veya daha büyük.

Olduğunda bir `CMapStringToString` nesnesi silindiğinde veya ne zaman öğeleri kaldırılır, `CString` nesneleri uygun şekilde kaldırılır.

Daha fazla bilgi için `CMapStringToString`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

##  <a name="cpair"></a>  CMapStringToString::CPair

Bir anahtar değeri ve ilişkili dize nesnenin değerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu bir sınıf içinde iç içe geçmiş yapısıdır [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).

Yapısı iki alandan oluşur:

- `key` Anahtar türü gerçek değeri.

- `value` İlişkili nesne değeri.

Dönüş değerleri depolamak için kullanılan [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), ve [CMapStringToString::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Örnek

  Kullanım örneği için örneğin bakın [CMapStringToString::PLookup](#plookup).

##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc

Eşlem nesnesine ilk girişinin döndürür.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki ilk giriş işaretçisi; bkz: [CMapStringToString::CPair](#cpair). Eşlem boşsa, değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi ilk öğeyi harita nesneyi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc

İşaret ettiği harita öğesini alır. *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Parametreler

*pAssoc*<br/>
Bir önceki tarafından döndürülen bir eşleme girişi işaret [PGetNextAssoc](#pgetnextassoc) veya [PGetFirstAssoc](#pgetfirstassoc) çağırın.

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki sonraki giriş işaretçisi; bkz: [CMapStringToString::CPair](#cpair). Eşlem içindeki son öğesi ise değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Eşlem içindeki tüm öğeleri arasında yineleme yapmak için bu yöntemi çağırın. İlk öğe ile bir çağrı almak `PGetFirstAssoc` ve art arda çağrılar haritayla yinelemek `PGetNextAssoc`.

### <a name="example"></a>Örnek

  Örneğin bakın [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMapStringToString::PLookup

Belirli bir anahtar ile eşlenen değeri arar.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğe anahtarı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtar için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Verilen anahtara tam olarak eşleşen bir anahtara bir eşleme öğeyi aramak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek Topla](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
