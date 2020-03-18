---
title: CMapStringToString sınıfı
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
ms.openlocfilehash: a2ffcf7ce7ee6eccc56382501a5969ddec6c9e22
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442597"
---
# <a name="cmapstringtostring-class"></a>CMapStringToString sınıfı

`CString` nesneleri tarafından girilen `CString` nesnelerinin eşlemelerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Üyeler

`CMapStringToString` üye işlevleri [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, üye işlevi özellikleri için `CMapStringToOb` başvuru belgelerini kullanabilirsiniz. Dönüş değeri veya "output" işlev parametresi olarak `CObject` bir işaretçi Gördüğünüz her yerde, **char**için bir işaretçi yerine koyun. Bir `CObject` işaretçisini "giriş" işlev parametresi olarak gördüğünüz her yerde **char**için bir işaretçi yerine koyun.

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

Örneğin, öğesine çevirir

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>Ortak yapılar

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToString:: CPair](#cpair)|Bir anahtar değeri ve ilişkili dize nesnesinin değerini içeren iç içe bir yapı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToString:: CMapStringToString](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToString:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapStringToString:: GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapStringToString:: GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMapStringToString:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapStringToString:: GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToString:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapStringToString:: InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tabloyu başlatır.|
|[CMapStringToString:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMapStringToString:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void işaretçi tuşuna bağlı olarak void bir işaretçi arar. İşaret ettiği varlık değil işaretçi değeri, anahtar karşılaştırması için kullanılır.|
|[CMapStringToString:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.|
|[CMapStringToString::P GetFirstAssoc](#pgetfirstassoc)|Haritadaki ilk `CString` yönelik bir işaretçi alır.|
|[CMapStringToString::P GetNextAssoc](#pgetnextassoc)|Yineleme için bir sonraki `CString` bir işaretçi alır.|
|[CMapStringToString::P arama](#plookup)|Değeri belirtilen değerle eşleşen bir `CString` için bir işaretçi döndürür.|
|[CMapStringToString:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapStringToString:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMapStringToString:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToString:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map içine bir öğe ekler — `SetAt`için işleç değiştirme.|

## <a name="remarks"></a>Açıklamalar

`CMapStringToString`, öğelerinin serileştirilmesi ve dökümünü desteklemek için `IMPLEMENT_SERIAL` makrosunu içerir. Bir eşleme bir arşive depolanıyorsa, aşırı yüklenmiş ekleme ( **<<** ) işleci veya `Serialize` member işleviyle birlikte her öğe sırayla serileştirilir.

Bireysel `CString`- `CString` öğelerin dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

`CMapStringToString` nesne silindiğinde veya öğeleri kaldırıldığında, `CString` nesneleri uygun şekilde kaldırılır.

`CMapStringToString`hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

##  <a name="cpair"></a>CMapStringToString:: CPair

Bir anahtar değeri ve ilişkili dize nesnesinin değerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu, [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)sınıfında yer alan iç içe bir yapıdır.

Yapı iki alandan oluşur:

- anahtar türünün gerçek değerini `key`.

- ilişkili nesnenin değerini `value`.

[CMapStringToString::P Lookup](#plookup), [cmapstringtostring::P GetFirstAssoc](#pgetfirstassoc)ve [cmapstringtostring::P GetNextAssoc](#pgetnextassoc)öğesinden dönüş değerlerini depolamak için kullanılır.

### <a name="example"></a>Örnek

  Kullanım örneği için [CMapStringToString::P Lookup](#plookup)örneğine bakın.

##  <a name="pgetfirstassoc"></a>CMapStringToString::P GetFirstAssoc

Map nesnesinin ilk girişini döndürür.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk girdinin işaretçisi; bkz. [CMapStringToString:: CPair](#cpair). Eşleme boşsa değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Map nesnesindeki ilk öğeyi bir işaretçi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

##  <a name="pgetnextassoc"></a>CMapStringToString::P GetNextAssoc

*Passocrec*tarafından işaret edilen harita öğesini alır.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Parametreler

*pAssoc*<br/>
Önceki bir [PGetNextAssoc](#pgetnextassoc) veya [PGetFirstAssoc](#pgetfirstassoc) çağrısı tarafından döndürülen bir Map girdisini işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Haritada bir sonraki girdiye yönelik bir işaretçi; bkz. [CMapStringToString:: CPair](#cpair). Öğe haritada son ise değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Haritadaki tüm öğeler arasında yinelemek için bu yöntemi çağırın. `PGetFirstAssoc` çağrısı olan ilk öğeyi alın ve sonra `PGetNextAssoc`için sonraki çağrılar ile haritada yineleyin.

### <a name="example"></a>Örnek

  [CMapStringToString::P GetFirstAssoc](#pgetfirstassoc)örneğine bakın.

##  <a name="plookup"></a>CMapStringToString::P arama

Verilen bir anahtara eşlenen değeri arar.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğenin anahtarına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Verilen anahtarla tam olarak eşleşen bir anahtarla bir map öğesi aramak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
